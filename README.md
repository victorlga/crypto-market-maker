# Crypto Market Maker

A simple cryptocurrency market maker written in Rust for learning purposes. This project connects to a cryptocurrency exchange (e.g., Binance Testnet) to stream real-time order book data, place limit orders, and manage account balances, providing a practical way to explore Rust's ecosystem.

## Features
- Streams real-time order book data via WebSocket.
- Places limit buy/sell orders based on a basic market-making strategy.
- Tracks account balances and open orders.
- Logs actions and errors for debugging.

## Getting Started

### Prerequisites
- Rust and Cargo: Install via `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`.
- A Binance Testnet account (optional, for testing with real API): [Binance Testnet](https://testnet.binance.vision/).

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/victorlga/crypto-market-maker.git
   cd crypto-market-maker
   ```
2. Build the project:
   ```bash
   cargo build
   ```

### Configuration
- Set environment variables for Binance API keys (for trading functionality):
  ```bash
  export BINANCE_API_KEY="your_api_key"
  export BINANCE_SECRET_KEY="your_secret_key"
  ```
- Configure logging level:
  ```bash
  export RUST_LOG=info
  ```

### Running
Run the market maker:
```bash
cargo run
```
This connects to Binance's WebSocket for BTC/USDT order book data and logs updates.

## Project Structure
- `src/main.rs`: Entry point, initializes the program.
- `src/exchange.rs`: Handles WebSocket and REST API interactions with the exchange.
- `src/order_book.rs`: Manages order book data and updates.
- `src/strategy.rs`: Implements the market-making strategy.
- `src/balance.rs`: Tracks account balances and open orders.
- `src/logger.rs`: Configures logging.
