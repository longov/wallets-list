# TON Connect Wallets

This repository contains the list of wallets that support TON Connect.

TON Connect [SDK](https://github.com/ton-connect/sdk) uses this list to present a choice of wallets so that dapp knows which bridge to use.

### Entry format

Each entry has the following format (subject to change):

```json
{
  "name": "Tonkeeper",
  "image": "https://tonkeeper.com/tonconnect-icon.png"
  "tondns":  "tonkeeper.ton",
  "about_url": "https://tonkeeper.com",
  "universal_url": "https://app.tonkeeper.com",
  "bridge_url": "https://bridge.tonkeeper.com",
  "js_bridge_key": "tonkeeper"
}
```

#### Description
- `name`: name of your wallet. Will be displayed in the dapp.
- `image`: icon of your wallet. Will be displayed in the dapp.
- `tondns`: (optional) will be used in the protocol later.
- `about_url`: info or landing page of your wallet. May be useful for TON newcomers.
- `universal_url`: (optional) base part of your wallet universal url. Your link should support [Ton Connect parameters](https://github.com/ton-connect/docs/blob/main/bridge.md#universal-link)
- `bridge_url`: (optional) url of your wallet's implementation of the [HTTP bridge](https://github.com/ton-connect/docs/blob/main/bridge.md#http-bridge).
- `js_bridge_key`: (optional) if your wallet handles [JS Bridge](https://github.com/ton-connect/docs/blob/main/bridge.md#js-bridge) connection, specify the binding for your bridge object accessible through `window`. Example: the key `"tonkeeper"` means the bridge can be accessed as `window.tonkeeper`.

If your wallet supports HTTP Bridge, you should specify `universal_url` and `bridge_url`. 
If your wallet provides the JS bridge (e.g. as a browser extension), you should specify the `js_bridge_key`.
If your wallet supports both bridges, you have to specify `universal_url`, `bridge_url` and `js_bridge_key`.

### How do I add my wallet?

Submit a [pull request](https://github.com/ton-connect/wallets-list/pulls) that modifies the list.

We will review correctness of the info (obviously we want this info to be provided by the wallet’s developer) and merge it promptly.

### What is the policy?

Our goal is to represent accurate up-to-date list of all TON wallets that support TON Connect.

In the future it would be a good idea to replicate wallet's info in a TON DNS record so that this repo simply lists the wallet domain names (to filter out spam), while developers have more direct control over the wallet parameters.