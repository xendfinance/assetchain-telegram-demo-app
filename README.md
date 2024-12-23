# Asset Chain Telegram Demo App

This project shows builders how to develop Telegram Mini Apps on Asset Chain. It uses Next.js, wagmi for 
Asset Chain wallet connections, and various injected providers for ease of use.

## Table of content
- [Getting Started](https://github.com/xendfinance/assetchain-telegram-demo-app#getting-started)
- [Contributing](https://github.com/xendfinance/assetchain-telegram-demo-app#contributing)
- [License](https://github.com/xendfinance/assetchain-telegram-demo-app#license)
- [Support](https://github.com/xendfinance/assetchain-telegram-demo-app#support)

## Getting Started

1. **Environment Variables**:  
   - Rename `.env.example` to `.env.local` and configure the following parameters:
     - `NEXT_PUBLIC_PROJECT_ID=""`: Add your project ID from [Reown](https://cloud.reown.com).
     - `NEXT_PUBLIC_INFURA_KEY=""`: Add your Infura API key from [Infura](https://www.infura.io).
     - `NEXT_PUBLIC_MANIFEST_URL=""`: Add a manifest URL.  
       Example: `"https://ton-connect.github.io/demo-dapp-with-react-ui/tonconnect-manifest.json"`.

2. **Clone the Repository**:  
   ```bash
   cd <cloned-repo>
   ```

3. **Install Dependencies**:  
   Run the following command to install the necessary packages:
   ```bash
   npm install
   ```

4. **Start the Development Server**:  
   Run the server locally:
   ```bash
   npm run dev
   ```

## Connecting to Injected Providers

To connect the app with different Ethereum wallet providers, you can modify the default connector in your `src/hooks/useEvmWallet.tsx` file based on your needs.

### Injected Providers Setup

1. **Use Injected Provider**:  
   This sets the default connector to detect and use any wallet injected into the browser, such as MetaMask or Coinbase Wallet.
   ```ts
   import { injected } from "@wagmi/core";
   const defaultConnector = injected();
   ```

2. **Use Coinbase Provider**:  
   To connect with Coinbase Wallet, change the configuration:
   ```ts
   import { coinbaseConfig } from "../configs/wagmiConfig";
   const defaultConnector = coinbaseConfig;
   ```

3. **Use MetaMask Provider**:  
   If you prefer MetaMask as your default wallet provider, configure it like so:
   ```ts
   import { metaMaskConfig } from "../configs/wagmiConfig";
   const defaultConnector = metaMaskConfig;
   ```

4. **Use WalletConnect Provider**:  
   To integrate WalletConnect, which supports mobile wallets, adjust the default connector to:
   ```ts
   import { walletConnectConfig } from "../configs/wagmiConfig";
   const defaultConnector = walletConnectConfig;
   ```

---

With this setup, you'll be able to connect your Telegram mini app to various Ethereum wallets, giving your users flexibility in interacting with blockchain-enabled features.

---

### Getting Started with Telegram Mini Apps

To start building a Telegram Mini App:

- **Read the Docs**: Visit the [Telegram Mini Apps Guide](https://core.telegram.org/bots/webapps#initializing-mini-apps) for steps to set up and initialize your app.

--- 

## Contributing

See [CONTRIBUTING.md](https://github.com/xendfinance/assetchain-telegram-demo-app/CONTRIBUTING.md) for contribution and pull request protocol. We expect contributors to follow our guide when submitting code or comments.

## License

[![License: GPL v3.0](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or suggestions, just say Hi on [Telegram](https://t.me/assetchainbuilders).<br/>
We're always glad to help.
