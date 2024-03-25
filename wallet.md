# Wallet Generation

**NOTE**: the values in this sample keychain output are not valid and is used for this example only. Your output _will_ look different.

This method creates a new stacks address (with corresponding Bitcoin address).
It's also fine to use an already existing stacks/bitcoin address(es)

**values shown below are 100% fake and are for documentation purposes only**

## Scripted install

If using the **Scripted install** section of [stacks-blockchain.md](./stacks-blockchain.md), and you opted to let the script created the keychain (stored at `/root/keychain.json`) then the following steps aren't needed.

## Generate stacks-blockchain keychain

**save this output in a safe place!**




```bash
$ cd $HOME && npm install @stacks/cli shx rimraf
$ npx @stacks/cli make_keychain 2>/dev/null | jq
{
  "mnemonic": "spare decade dog ghost luxury churn flat lizard inch nephew nut drop huge divert mother soccer father zebra resist later twin vocal slender detail",
  "keyInfo": {
    "privateKey": "ooxeemeitar4ahw0ca8anu4thae7aephahshae1pahtae5oocahthahho4ahn7eici",
    "address": "STTXOG3AIHOHNAEH5AU6IEX9OOTOH8SEIWEI5IJ9",
    "btcAddress": "Ook6goo1Jee5ZuPualeiqu9RiN8wooshoo",
    "wif": "rohCie2ein2chaed9kaiyoo6zo1aeQu1yae4phooShov2oosh4ox",
    "index": 0
  }
}
```

## Create bitcoin wallet and import it into this instance

We'll be using the wallet values from the previous `npx` command, "btcAddress" and "wif"
_Import will only be successful after bitcoin has fully synced_

```bash
bitcoin-cli createwallet "your-wallet-name" false false "" false false true

bitcoin-cli -rpcwallet=your-wallet-name importprivkey "YOUR_PRIVATE_KEY_WIF_HERE"



```

Once imported, the wallet will need to be funded with some bitcoin.

THEN YOU MUST ACTUALLY FUND YOUR BITCOIN MINING WALLET USING THE BTCADDRESS FROM YOUR KEYCHAIN WHICH IS NOW LINKED TO YOUR BITCOIN-QT OR BITCOIND AND CHECK FOR UTXOs AND YOUR BITCOIN-QT WALLET MUST BE RUNNING WHILE YOU USE STACKS-CORE NODE AND IT MUST BE 100% SYNCED with a CHECKMARK

