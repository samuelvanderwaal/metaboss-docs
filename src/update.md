## Update

**Warning: These commands modify your NFT and are for advanced users. Use with caution.**

Update various aspects of an NFT.

#### Update Data

Update the `Data` struct on a NFT from a JSON file.

##### Usage

```bash
metaboss update data --keypair <PATH_TO_KEYPAIR> --account <MINT_ACCOUNT> --new-data-file <PATH_TO_NEW_DATA_FILE>
```

The JSON file should include all the fields of the metadata `Data` struct and should match `creator` `verified` bools for existing creators. E.g. if your NFT was minted by the Metaplex Candy Machine program, and you wish to keep your candy machine as a verified creator _you must add the candy machine to your creators array with `verified` set to `true`_.

Note: The on-chain `Data` struct is *different* than the external metadata stored at the link in the `uri` field so make you understand the difference before running this command.

**Make sure you understand how the Metaplex Metadata `Data` struct works and how this command will affect your NFT. Always test on `devnet` before running on mainnet.**

```json
{
    "name": "FerrisCrab #4",
    "symbol": "FERRIS",
    "uri": "https://arweave.net/N36gZYJ6PEH8OE11i0MppIbPG4VXKV4iuQw1zaq3rls",
    "seller_fee_basis_points": 100,
    "creators": [
        {
            "address": "<YOUR_CANDY_MACHINE_ID>",
            "verified": true,
            "share": 0
        },
        {
            "address": "<KEYPAIR_CREATOR>",
            "verified": true,
            "share": 50
        },
        {
            "address": "42NevAWA6A8m9prDvZRUYReQmhNC3NtSZQNFUppPJDRB",
            "verified": false,
            "share": 50
        }
    ]
}
```

Outputs a TxId to the command line so you can check the result.

#### Update Data All

Update the `Data` struct on a list of NFTs from JSON files.

##### Usage

```bash
metaboss update data-all --keypair <PATH_TO_KEYPAIR> --data-dir <PATH_TO_DATA_DIR>
```

Each JSON file in the data directory should include the mint account and all the fields of the metadata `Data` struct and should match `creator` `verified` bools for existing creators. E.g. if your NFT was minted by the Metaplex Candy Machine program, and you wish to keep your candy machine as a verified creator _you must add the candy machine to your creators array with `verified` set to `true`_.

Note: The on-chain `Data` struct is *different* than the external metadata stored at the link in the `uri` field so make you understand the difference before running this command.

**Make sure you understand how the Metaplex Metadata `Data` struct works and how this command will affect your NFT. Always test on `devnet` before running on mainnet.**

```json
{
    "mint_account": "CQNKXw1rw2eWwi812Exk4cKUjKuomZ2156STGRyXd2Mp",
    "nft_data":
    {
    "name": "FerrisCrab #4",
    "symbol": "FERRIS",
    "uri": "https://arweave.net/N36gZYJ6PEH8OE11i0MppIbPG4VXKV4iuQw1zaq3rls",
    "seller_fee_basis_points": 100,
    "creators": [
        {
            "address": "<YOUR_CANDY_MACHINE_ID>",
            "verified": true,
            "share": 0
        },
        {
            "address": "<KEYPAIR_CREATOR>",
            "verified": true,
            "share": 50
        },
        {
            "address": "42NevAWA6A8m9prDvZRUYReQmhNC3NtSZQNFUppPJDRB",
            "verified": false,
            "share": 50
        }
    }
}
```

Outputs a TxId to the command line so you can check the result.

#### Update URI

Update the metadata URI, keeping the rest of the `Data` struct the same.

##### Usage

```bash
metaboss update uri --keypair <PATH_TO_KEYPAIR> --account <MINT_ACCOUNT> --new-uri <NEW_URI>
```

#### Update URI All

Update the metadata URI for a list of mint accounts, keeping the rest of the `Data` struct the same.

##### Usage

```bash
metaboss update uri-all --keypair <PATH_TO_KEYPAIR> --json-file <PATH_TO_JSON_FILE>
```

```json
[
    {
        "mint_account": "xZ43...",
        "new_uri": "https://arweave.net/N36gZYJ6PEH8OE11i0MppIbPG4VXKV4iuQw1zaq3rls"
    },
        {
        "mint_account": "71bk...",
        "new_uri": "https://arweave.net/FPGAv1XnyZidnqquOdEbSY6_ES735ckcDTdaAtI7GFw"
    }
]
```