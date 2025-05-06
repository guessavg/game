# 🎮 Guess Two‑Thirds Game (Web3 dApp on **Base**)

This project is a decentralized version of the classic **“Guess 2 / 3 of the Average”** game‑theory experiment.  
Players participate **on‑chain** by sending ETH on **Base**; the contribution that lands closest to **2 / 3 of the average** wins the prize pool (minus a 1 % fee).

---

## 🌐 Live App

Play it here:

**https://guessavg.github.io/game/**   <!-- update if you host under a new domain -->

---

## 📦 Features

- MetaMask (or any EIP‑1193 wallet) connect  
- One‑click **add / switch to Base network**  
- Join a round by sending **any amount of ETH**  
- Real‑time UI showing  
  - Current round ID  
  - Player list & stakes  
  - Contract balance  
  - Last winner & reward  
- Built with **ethers.js v6**

---

## ⚙️ How It Works

1. Users send ETH to the contract’s `play()` function.  
2. A pseudo‑random stop‑condition (parametrised at deployment) decides when the round ends.  
3. The stake closest to **2 / 3 × average** wins; ties are broken by earliest entry.  
4. Winner receives the pool minus a 1 % fee to the owner.  
5. Front‑end polls on‑chain data and past `GameEnded` events for live updates.

---

## 🔧 Smart Contract Info

| Item | Value |
|------|-------|
| **Contract address** | `0x4BbeE9F876ff56832E724DC9a7bD06538C8868D2` |
| **Network RPC** | `https://base-rpc.publicnode.com` |
| **Chain ID** | 8453 (`0x2105`) |
| **Block explorer** | <https://basescan.org> |

---

## 🧪 Tech Stack

- Vanilla **HTML / JavaScript**  
- **ethers.js** v6  
- **MetaMask** (EIP‑1193 provider)  
- Static hosting (e.g. GitHub Pages)

---

## 📄 Contract ABI (used in front‑end)

```json
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
