# Ai Trading Bot

A Model Context Protocol (MCP) server that bridges AI models with the Zerodha trading platform. This project provides a streamlined interface to execute trades, monitor portfolio performance, and manage open positions via Zerodha.

## Features

- 🔐 Secure authentication with Zerodha API

- 📊 Portfolio overview and holdings

- 📈 View open positions

- 💹 Execute buy/sell orders

- 👤 Retrieve user profile details


## Prerequisites

- Node.js (v14 or higher)
- Zerodha Trading Account
- API credentials from Zerodha

## Installation

1. Clone the repository:
```bash
https://github.com/suryansh4424/AI-Trading-Bot.git
cd AI-Trading-Bot
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory with your Zerodha credentials:
```env
KITE_API_KEY=your_api_key
KITE_SECRET_KEY=your_secret_key
REQUEST_TOKEN=your_request_token
ACCESS_TOKEN=your_access_token
```

## Claude Desktop MCP Configuration

To use this MCP server with Claude Desktop, you need to configure the mcp server details. Here's how to set it up:

1. Open `claude_desktop_config.json` in your project root
2. Add the following configuration:
```json
{
  "mcpServers": {
    "tradeStocks": {
      "command": "/opt/homebrew/bin/bun",
      "args": [
        "/path/to/your/index.ts"
      ], 
      "env": {
        "KITE_API_KEY": "your_api_key",
        "KITE_SECRET_KEY": "your_secret_key",
        "REQUEST_TOKEN": "your_request_token",
        "ACCESS_TOKEN": "your_access_token"
      }
    }
  }
}
```

Make sure to:
- Update the path to your `index.ts` file
- Replace the environment variables with your actual Zerodha credentials

## Usage

The MCP server provides the following tools:

### Get Profile
```typescript
get-profile
```
Retrieves the user's profile information from Zerodha.

### Buy Stock
```typescript
buy-stock {stock: string, quantity: number}
```
Places a buy order for the specified stock and quantity.

### Sell Stock
```typescript
sell-stock {stock: string, quantity: number}
```
Places a sell order for the specified stock and quantity.

### Show Portfolio
```typescript
show-portfolio
```
Displays the user's complete portfolio holdings.

### Show Positions
```typescript
show-positions
```
Shows the user's open positions.

## Development

The project is built using:
- TypeScript
- KiteConnect API
- Model Context Protocol (MCP) SDK
- Zod for schema validation
