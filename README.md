
# Runestone Distribution Engine

A robust backend system built with Node.js and Express for handling Rune token airdrops with support for both same-amount and different-amount distributions.

## Technical Overview

This server application provides API endpoints for executing and estimating Rune token airdrop transactions. The system includes fee calculation, transaction estimation, and support for large-scale distributions with built-in rate limiting and comprehensive documentation.

## Project Structure

```
root/
├── config/                 # Configuration settings
├── routes/                 # API route handlers
│   ├── AirdropRoute/       # Airdrop distribution endpoints
│   ├── EstimateRoute/      # Transaction estimation endpoints
│   └── SubRoute/           # Additional utility endpoints
├── service/psbt/           # PSBT transaction services
├── test/                   # Test suites
├── utils/                  # Utility functions and API clients
│   ├── blockcypher.api.ts  # Blockchain data provider
│   ├── mempool.api.ts      # Mempool integration
│   └── unisat.api.ts       # Unisat API integration
├── swagger.yaml            # API documentation
└── configuration files
```

## Installation & Setup

1. **Clone the repository:**
```bash
git clone https://github.com/blixor7/rune-airdrop-backend.git
cd rune-airdrop-backend
```

2. **Install dependencies:**
```bash
yarn install
```

3. **Configure environment:**
```bash
cp .env.example .env
# Edit .env with your configuration
PORT=your-port
```

4. **Start the server:**
```bash
yarn dev
```

## API Documentation

Interactive API documentation is available via Swagger UI at `/api-docs` when the server is running.

## Core Endpoints

### Airdrop Distribution
- `POST /api/same-amount` - Distribute equal amounts to multiple addresses
- `POST /api/different-amount` - Distribute custom amounts to addresses
- `POST /api/large-different-amount` - Handle large-scale distributions

### Transaction Estimation
- `POST /api/estimate/same-amount` - Estimate fees for same-amount airdrops
- `POST /api/estimate/different-amount` - Estimate fees for custom distributions

### Utility Endpoints
- `GET /api/runestone-fee` - Calculate transaction fees
- `GET /` - Health check endpoint

## Features

- **PSBT Transaction Handling** - Secure transaction creation and signing
- **Rate Limiting** - Mutex-based API protection
- **Multiple Blockchain APIs** - Integration with BlockCypher, Mempool, and Unisat
- **Comprehensive Testing** - Test suites for critical functionality
- **Swagger Documentation** - Interactive API documentation

## Security & Performance

- CORS enabled for cross-origin requests
- JSON body parsing with express.json
- Global wallet management with iterator tracking
- Error handling with appropriate HTTP status codes

## Development

The project uses TypeScript for type safety and includes extensive test coverage. Contributions are welcome through the issue tracker and pull requests.
