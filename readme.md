# EVM MCP Server

A VS Code Model Context Protocol (MCP) server enabling AI agents to access and interact with EVM blockchain data.

## Overview

This server implements the Model Context Protocol to provide AI assistants with real-time access to Ethereum and other EVM-compatible blockchain networks. By integrating with VS Code's MCP infrastructure, the server allows AI agents to query blockchain data, check account balances, identify smart contracts, and monitor gas prices across multiple supported networks.

## Features

- **Multi-Chain Support**: Access data from Ethereum, Base, Arbitrum, Avalanche, and Binance Smart Chain
- **Balance Queries**: Check native token balances for any address
- **Contract Detection**: Determine if an address is a smart contract or externally owned account (EOA)
- **Gas Price Monitoring**: Get current gas prices across supported chains
- **MCP Compliance**: Built using the official Model Context Protocol SDK

## Prerequisites

- Node.js 18.x or higher
- QuickNode API access 
- VS Code with MCP support

## Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   npm install
   # or
   pnpm install
   ```
3. Set up environment variables (see Configuration section)
4. Build the project:
   ```bash
   npm run build
   # or
   pnpm build
   ```
5. Start the server:
   ```bash
   npm start
   # or
   pnpm start
   ```

## Configuration

Create a `.env` file in the root directory with the following variables:

```
# QuickNode API Configuration
QN_ENDPOINT_NAME=your-quicknode-endpoint
QN_TOKEN_ID=your-quicknode-token-id

# Optional: Alternative RPC endpoints
# ETHEREUM_RPC=https://your-ethereum-rpc-url
# BASE_RPC=https://your-base-rpc-url
# ARBITRUM_RPC=https://your-arbitrum-rpc-url
# AVALANCHE_RPC=https://your-avalanche-rpc-url
# BSC_RPC=https://your-bsc-rpc-url
```

### API Configuration

The server requires access to blockchain RPC endpoints. By default, it uses QuickNode as the RPC provider. You'll need to:

1. Sign up for a [QuickNode account](https://www.quicknode.com/)
2. Create endpoints for each blockchain you want to support
3. Add your endpoint name and token ID to the environment variables

Alternatively, you can use any other RPC provider by configuring the optional RPC endpoint variables in your `.env` file.

## Available Tools

### eth_getBalance

Retrieves the native token balance of an address.

```json
{
  "address": "0x...", // Valid Ethereum address
  "chain": "ethereum" // One of: ethereum, base, arbitrum, avalanche, bsc
}
```

### eth_getCode

Determines if an address is a contract or wallet.

```json
{
  "address": "0x...", // Valid Ethereum address
  "chain": "ethereum" // One of: ethereum, base, arbitrum, avalanche, bsc
}
```

### eth_gasPrice

Gets the current gas price on the specified chain.

```json
{
  "chain": "ethereum" // One of: ethereum, base, arbitrum, avalanche, bsc
}
```

## Integration with VS Code

This server is designed to be used with VS Code's Model Context Protocol extension. When properly configured, VS Code AI assistants can access blockchain data directly through natural language queries.

## License

ISC

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
