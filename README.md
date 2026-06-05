# xArtists DApp

## Description

xArtists is a decentralized art platform built on the MultiversX blockchain. It empowers artists by tokenizing physical artworks as NFTs, integrating AI-powered quality assessments and escrow mechanisms for physical claims.

**Key Features:**
- Create and manage NFTs linked to physical art
- AI analysis and reassessment of artworks (via GPT integration)
- Purchase, staking, and governance features (TRO token)
- Escrow system for physical artwork claims
- MultiversX integration for secure, transparent transactions

This is a full-stack DApp (client/server/shared) with React frontend, Express backend, and Drizzle ORM.

**Note:** Original demo limitations addressed in this updated version:
- Hardcoded localhost URLs removed
- Image URL parsing fixed
- Recommendations for guards, dynamic collections/pricing, and production security added
- SDK updated guidance to latest modular v5+

## Tech Stack

- **Frontend**: React 18, Vite, TypeScript, Tailwind CSS, shadcn/ui (Radix), Wouter for routing
- **Backend**: Express, Node.js, TypeScript, Drizzle ORM (Neon PostgreSQL)
- **Blockchain**: MultiversX (@multiversx/sdk-core, @multiversx/sdk-dapp)
- **Other**: React Hook Form, Zod validation, Framer Motion, Recharts, etc.

## Setup Instructions

### Prerequisites
- Node.js >= 20
- pnpm or yarn/npm
- MultiversX wallet (xPortal or extension)
- Neon DB or PostgreSQL instance

### Installation

```bash
# Clone the repo
git clone https://github.com/Neltud/xArtists-dapp.git
cd xArtists-dapp

# Install dependencies
yarn install  # or npm install

# Setup environment
cp .env.example .env
# Edit .env with your DB URL, MultiversX config, OpenAI key, etc.

# Push DB schema
yarn db:push

# Run dev server
yarn dev
```

Build for production:
```bash
yarn build
yarn start
```

## MultiversX Integration

- Uses @multiversx/sdk-dapp v3.1.6 (recommend migrating to latest v5+ for modular architecture and better AI agent support)
- Features: NFT creation, staking (TRO), governance, faucet integration
- Network: Devnet for demo, migrate to Mainnet for production

**Important Corrections & Security Notes:**
- Removed all hardcoded localhost URLs
- Fixed reassessment image URL parsing
- **Production Recommendations:**
  - Implement smart contract guards/roles (owner-only, verified escrow)
  - Add dynamic collections and flexible pricing
  - Secure backend API (auth, rate limiting)
  - Audit contracts
  - Use mainnet and proper env separation

## Project Structure

- `client/`: React frontend (UI components, artwork gallery, transactions)
- `server/`: Express backend (AI queries, DB, API)
- `shared/`: Shared types/schemas
- `attached_assets/`: Design assets

## Recent Updates (Corrected Version)
- Fixed image handling and URLs
- Integrated faucet, NFT staking, TRO governance
- Prepared for backend AI integration
- Added this comprehensive README and production guidelines

## Demo & Links

- Original Demo: https://xartists-demo.erd-works.com/
- MultiversX Explorer for transactions
- Contact: @tudurioriginal on X

## License
MIT

## Contributing
Pull requests welcome! Focus on security, UX, and MultiversX best practices.

---

*Updated and corrected for production readiness - June 2026*