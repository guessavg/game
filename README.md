# 🎮 Guess Two-Thirds Game (Web3 dApp)

This project is a decentralized game based on the classic **"Guess 2/3 of the Average"** game theory experiment. It is built as a Web3 dApp, allowing players to participate on-chain by sending OIIA tokens. The closest player to 2/3 of the average wins the prize pool.

## 🌐 Live App

You can try the game live at:

**https://guessavg.github.io/**

## 📦 Features

- Connect with MetaMask
- One-click add/switch to Oiia Network
- Join game by sending any amount of OIIA
- View:
  - Current round
  - List of players and their amounts
  - Contract balance
  - Last winner and reward
- Uses `ethers.js` v6 for blockchain interaction

## ⚙️ How It Works

- Users send OIIA to join the current round.
- Once the round ends (according to random logic in the contract), the player whose value is closest to **2/3 of the average** wins.
- Winner receives the total pool minus a 1% fee.
- The UI displays current round, players, balance, and last winner details.

## 🔧 Smart Contract Info

- **Contract Address:** `0x6eb079c9d3005bd596e8a0e5065fa33c80aba8f1`
- **Network RPC:** `https://rpc.oiia.network`
- **Chain ID:** `20220915 (0x1348BF3)`
- **Block Explorer:** [https://explorer.oiia.network](https://explorer.oiia.network)

## 🧪 Technologies Used

- HTML / JavaScript
- ethers.js v6
- MetaMask
- Hosted on GitHub Pages

## 📄 Sample Contract ABI (Used in the App)

```
[
  "function gameId() view returns (uint256)",
  "function players(uint256) view returns (address addr, uint256 amount)",
  "function play() payable",
  "function hasPlayed(address) view returns (bool)",
  "event PlayerJoined(address indexed player, uint256 amount)",
  "event GameEnded(uint256 indexed gameId, address winner, uint256 reward, uint256 guessTarget)"
]
```

## 🚀 Run Locally

To test this dApp locally, use any HTTP server:

```
# Python 3
python -m http.server
```

Then visit `http://localhost:8000` in your browser.

> ⚠️ Opening `file://` URLs directly will cause MetaMask injection to fail. Always use a local server.

## 🛠️ Troubleshooting

- **"MetaMask not detected"** → Ensure MetaMask is installed and page is served over HTTP/HTTPS.
- **"Failed to add Oiia Network"** → Try upgrading MetaMask, or ensure you're not using a mobile browser.
- **Wallet not connecting** → Check browser extension permissions for GitHub Pages.

## 📜 License

MIT License.
