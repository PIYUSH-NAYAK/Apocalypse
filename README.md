# 🧟 Apocalypse

A 3D multiplayer zombie survival game built with React Three Fiber, Rapier physics, and Solana blockchain integration. Fight zombies, collect weapons, and battle other players in a post-apocalyptic world.

---

## ✨ Features

- **Singleplayer Survival** — Wave-based zombie spawning with dynamic AI, combat, and health system
- **Multiplayer** — Real-time WebSocket multiplayer with player syncing via a Node.js server
- **Characters** — 4 playable characters (Lis, Matt, Sam, Shaun) with dual-weapon variants and companion pets (German Shepherd, Pug)
- **Weapons** — 7 weapons: Pistol, Rifle, SMG, Axe, Knife, Spear, Guitar — each with unique stats
- **Zombies** — 4 zombie variants (Basic, Chubby, Ribcage, Arm) with physics-based combat
- **Atmosphere System** — Dynamic 24-hour day/night cycle with dread lighting and post-processing effects
- **Minimap** — Real-time overhead minimap showing player and zombie positions
- **Solana Integration** — Wallet connection, on-chain profile, session keys via Magicblock ephemeral rollups
- **Inventory System** — In-game inventory and character selection screen

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Rendering | [React Three Fiber](https://github.com/pmndrs/react-three-fiber) + [Three.js](https://threejs.org) |
| Physics | [@react-three/rapier](https://github.com/pmndrs/react-three-rapier) |
| Post-processing | [@react-three/postprocessing](https://github.com/pmndrs/react-postprocessing) |
| 3D Helpers | [@react-three/drei](https://github.com/pmndrs/drei) |
| State | [Zustand](https://github.com/pmndrs/zustand) |
| Routing | React Router v7 |
| Blockchain | [@solana/web3.js](https://github.com/solana-labs/solana-web3.js), [@coral-xyz/anchor](https://github.com/coral-xyz/anchor) |
| Rollups | [Magicblock Ephemeral Rollups SDK](https://github.com/magicblock-labs) |
| Multiplayer | Node.js + Express + WebSocket (`ws`) |
| Build | Vite + TypeScript |

---

## 📁 Project Structure

```
Apocalypse/
├── src/
│   ├── components/
│   │   ├── Characters/          # Playable character GLTF components
│   │   ├── Zombies/             # Zombie variants + spawner
│   │   ├── Character.tsx        # Main character controller
│   │   ├── Experience.tsx       # Main scene
│   │   ├── Map.tsx              # Game world / environment
│   │   ├── UI.tsx               # Full game HUD & menus
│   │   ├── Multiplayer.tsx      # Remote player manager
│   │   ├── AtmosphereEffects.tsx # Day/night + lighting
│   │   ├── Minimap.tsx          # Overhead minimap
│   │   └── ...
│   ├── hooks/
│   │   ├── useSocket.ts         # WebSocket multiplayer hook
│   │   ├── useBattle.ts         # On-chain battle hook
│   │   ├── useProfile.ts        # Solana profile hook
│   │   └── useGameProgram.ts    # Anchor program hook
│   ├── config/
│   │   ├── GameConfig.ts        # Weapon stats, character config
│   │   └── EnvironmentConfig.ts # Scene environment settings
│   ├── store.ts                 # Global Zustand game state
│   └── App.tsx                  # Routes & canvas setup
├── public/
│   ├── models/                  # Optimized .glb character models
│   ├── weapons/                 # Weapon GLTF models
│   └── environement/            # Environment prop GLTFs
├── node-server/                 # WebSocket multiplayer server
└── apocalypse-contracts/        # Solana smart contracts (Anchor)
```

---

## 🎮 Controls

| Key | Action |
|---|---|
| `W A S D` / Arrow Keys | Move |
| `Space` | Jump |
| `Shift` | Sprint |
| `1` – `0` | Switch weapon slot |
| `Y` | Call pet |
| `G` | Pet your companion |

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- npm or bun

### Install & Run

```bash
# Clone the repo
git clone https://github.com/PIYUSH-NAYAK/Apocalypse.git
cd Apocalypse

# Install dependencies
npm install

# Start the frontend
npm run dev
```

### Run the Multiplayer Server

```bash
cd node-server
npm install
npm run dev
```

The WebSocket server runs on `ws://localhost:PORT/ws` by default.

---

## 🗺️ Routes

| Route | Description |
|---|---|
| `/` | Default scene (level 3) |
| `/singleplayer` | Singleplayer survival mode |
| `/multiplayer` | Multiplayer lobby & battle |
| `/inventory` | Character & inventory screen |
| `/scene1` – `/scene5` | Individual game scenes |

---

## ⛓️ Solana / Blockchain

- Wallet connection via `@solana/wallet-adapter`
- On-chain player profiles stored via Anchor program
- Session-based gasless transactions using **Magicblock Ephemeral Rollups**
- Smart contracts located in `apocalypse-contracts/`

---

## 📜 License

MIT
