# L2 Frontier: Web3 Scaling & Cryptographic Hub
An ultra-premium, interactive Web3 educational portal built to explain Ethereum scaling, core decentralized concepts, live market pricing, and blockchain cryptographic consensus.
Designed as an educational tool, this multi-page platform stands out by incorporating live interactive widgets, HTML5 Canvas simulations, real-time API integrations, and client-side cryptographic engines.
---
## 🚀 Key Features & Differentiators
This project implements advanced elements to elevate it above typical classroom templates:
1. **Interactive L2 Rollup Simulator (Page 1)**
   - Renders a live, visual representation of transaction flows.
   - Users queue transactions, see off-chain compression at the L2 Sequencer level, and watch them settle on Ethereum L1.
   - Calculates and displays real-time gas costs, showing gas saving metrics (e.g., $15.50 L1 cost vs. $0.25 L2 cost).
2. **3D Tilting Cards & Reputation Quiz (Page 2)**
   - Displays foundational concepts (Web2 vs. Web3, BTC vs. ETH, Cryptography, Blockchain vs. Database) as cards that react to cursor coordinates in 3D perspective space.
   - Click cards to flip them and view actual smart contract source code, secp256k1 curves, and JSON-RPC payloads.
   - Features a self-scoring reputation quiz that assigns a customized Web3 developer rating badge (e.g., "Solidity Wizard").
3. **Live Prices with Sparklines & Gas Calculator (Page 3)**
   - Integrates CoinGecko's Market API to fetch live rates for BTC, ETH, SOL, and ARB.
   - Renders real-time, animated SVG sparkline charts displaying 7-day price trends.
   - Implements a resilient `localStorage` cache: if the CoinGecko public API rate-limits requests, the portal displays cached data with a notification banner instead of crashing.
   - Includes a dynamic Gas Cost Calculator comparing mainnet Ethereum L1 to Arbitrum L2, taking custom Gwei and transaction types (Transfers, Swaps, Mints) into account.
4. **Consensus & Immutability Lab (Page 4)**
   - Implements block creation using the browser's native **Web Crypto API (SHA-256)** for standard, zero-dependency cryptography.
   - Allows users to add an arbitrary number of blocks.
   - Modifying block contents dynamically triggers a cascading chain reaction, turning subsequent block links red (Invalid) to show cryptographic linkage.
   - Users select target mining difficulties (1 to 4 zeros) and watch block nonces calculate with a live hashes-per-second indicator.
---
## 📁 Repository Structure
```bash
web3-edu-site/
│
├── index.html        # Home & Interactive Rollup Sequencer
├── concepts.html     # 3D comparison cards & Interactive Quiz
├── prices.html       # CoinGecko dashboard, SVG Sparklines & Gas Calculator
├── simulator.html    # Web Crypto SHA-256 Multi-Block Simulator
├── style.css         # Foundational dark cyberpunk styling system
└── README.md         # Documentation & Setup instructions
```
---
## 🛠️ Installation & Local Execution
Because the website is built with vanilla HTML, CSS, and Javascript, it has **zero external package dependencies** and can be run without compiling or setting up complex runtimes.
### Option 1: Double-Click (Simple)
Simply navigate to the project directory and double-click `index.html` to open it directly in any modern web browser.
### Option 2: Local Static Server (Recommended)
To prevent cross-origin restrictions on some advanced browser APIs, it is recommended to serve files via a local server:
**Using Python:**
```bash
python -m http.server 8000
```
Open your browser and navigate to `http://localhost:8000`.
**Using Node.js (http-server):**
```bash
npx http-server -p 8000
```
Navigate to `http://localhost:8000`.
---
## 🔮 Future Enhancements & Roadmap
- **Wallet Connection**: Implement a mock or actual MetaMask (`window.ethereum`) connect button to display real user addresses.
- **Rollup Dispute Simulation**: Add a "Submit Fraud Challenge" button to page 1 to demonstrate how validators verify assertions during the dispute window.
- **Persistent Tracker**: Enable persistent custom coin selections in Page 3 across browser restarts.
- **Multithreaded Mining**: Move the hashing engine in Page 4 to Web Workers to prevent UI freezing at higher difficulties (e.g. 5+ zeros).
