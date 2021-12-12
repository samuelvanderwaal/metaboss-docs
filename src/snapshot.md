## Snapshot

Get snapshots of various blockchain states.

#### Snapshot CM-Accounts

Snapshot all candy machine config and state accounts for a given update_authority.

##### Usage

```bash
metaboss snapshot cm-accounts --update-authority <UPDATE_AUTHORITY> --output <OUTPUT_DIR>
```

Creates a JSON file in the output directory with the name format of `<UPDATE_AUTHORITY>_accounts.json`, consisting of an object with the fields `config_accounts` and `candy_machine_accounts`:

```json
{
    "config_accounts": [
        {
            "address": "2XBqwwTLf24ACPR3BDSEKCB95PZiAwYySeX1LyN3FKDL",
            "data_len": 1456
        },
        {
            "address": "9tNkktGZhLiWHkc4JhoTYvMLXEVA8qauSVeFwyiRPCsT",
            "data_len": 1216
        }
    ],
    "candy_machine_accounts": [
        {
            "address": "DwoPaGFxJpGRq3kZQBNfBroCGaS9Hdg2rpFHJpD2iBhW",
            "data_len": 529
        },
        {
            "address": "CpFAvcReAkmxWiL7jwDjBKD9jX1Bi1Lky4bHwMkgCuxc",
            "data_len": 529
        }
    ]
}
```

#### Snapshot Holders

Snapshot all current holders of NFTs filtered by candy_machine_id or update_authority

##### Usage

```bash
metaboss snapshot holders --candy-machine-id <CANDY_MACHINE_ID> --output <OUTPUT_DIR>
```

or

```bash
metaboss snapshot holders --update-authority <UPDATE_AUTHORITY> --output <OUTPUT_DIR>
```

Creates a JSON file in the output directory with the name format of `<CANDY_MACHINE_ID/UPDATE_AUTHORITY>_holders.json` consisting of an array of objects with the following fields:

-   owner wallet -- the holder of the token
-   associated token account -- the token account the NFT is stored at
-   mint account -- the token mint account for the NFT
-   metadata account -- the metadata account decorating the mint account that defines the NFT

Example file:

```json
[
    {
        "owner_wallet": "42NevAWA6A8m9prDvZRUYReQmhNC3NtSZQNFUppPJDRB",
        "associated_token_address": "7yGA66LYDU7uoPW2x9jrUKaDWTs9jqZ5cSNKR1VaLQdw",
        "mint_account": "C2eGm8iQPnKVWxakyo8QhwJUvYrZHKF52DPQuAejpTWG",
        "metadata_account": "8WTA3sLxwRNDKHxZFbn2CFo3FX1ZP59EqrvuDPLbmmWV"
    }
]
```

#### Snapshot Mints

Snapshot all mint accounts for a given candy machine id or update authority

##### Usage

```bash
metaboss snapshot mints --candy-machine-id <CANDY_MACHINE_ID> --output <OUTPUT_DIR>
```

or

```bash
metaboss snapshot mints --update-authority <UPDATE_AUTHORITY> --output <OUTPUT_DIR>
```

Creates a JSON file in the output directory with the name format of `<CANDY_MACHINE_ID/UPDATE_AUTHORITY>_mint_accounts.json` consisting of an array of mint accounts.

```json
[
    "CQNKXw1rw2eWwi812Exk4cKUjKuomZ2156STGRyXd2Mp",
    "5pgGJ5npeMxBzTiQctDgoofEVGSwZMYm3QMz4F4NDShz",
    "8GcRqxy4VAocTcAkoxCXkPCEmM36HMtjBc8ZarWhAD6o"
]
```