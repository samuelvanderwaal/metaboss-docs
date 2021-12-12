## Sign

**Warning: These commands modify your NFT and are for advanced users. Use with caution.**

Sign metadata for an unverified creator.

#### Sign One

Sign the metadata for a single mint account.

##### Usage

```bash
metaboss sign one --keypair <PATH_TO_KEYPAIR> --account <MINT_ACCOUNT>
```

Outputs a TxId to the command line so you can check the result.

#### Sign All

Sign all metadata from a JSON list or for a given candy machine id.

##### Usage

```bash
metaboss sign all --keypair <PATH_TO_KEYPAIR> --candy-machine-id <CANDY_MACHINE_ID>
```

```bash
metaboss sign all --keypair <PATH_TO_KEYPAIR> --mint-accounts-file <PATH_TO_MINT_ACCOUNTS_FILE>
```

For the latter usage, the mint accounts file should be a JSON file with a list of mint accounts to be signed:

```json
[
    "C2eGm8iQPnKVWxakyo8QhwJUvYrZHKF52DPQuAejpTWG",
    "8GcRqxy4VAocTcAkoxCXkPCEmM36HMtjBc8ZarWhAD6o",
    "CK2npuck3WTRNFXSdZv8YjudJJEa69EVGd6GFfeSzfGP"
]
```

Outputs a TxId to the command line so you can check the result.
