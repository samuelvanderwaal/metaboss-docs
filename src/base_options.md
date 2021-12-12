## Base Options

These are the options you pass directly to the metaboss command before the subcommands.

```bash
metaboss <option> <subcommand> <subcommand>
```

## Options

-r, --rpc <rpc> The RPC endpoint to use for commands.

Metaboss will try to read your Solana config settings for both the RPC endpoint and also the Commitment setting by reading from `$HOME/.config/solana/cli/config.yml`. If it can't find a config file it defaults to using ` https://api.devnet.solana.com` and `confirmed`.

Running Metaboss with the `--rpc` option will override the above with whatever RPC endpoint the user provides.

-t, --timeout <timeout> The timeout in seconds to use for RPC calls.

This defaults to 60 seconds which should be fine for most cases but can be overriden if needed.

Example:

```bash
metaboss -r https://api.devnet.solana.com -t 120 snapshot holders -u DC2mkgwhy56w3viNtHDjJQmc7SGu2QX785bS4aexojwX
```