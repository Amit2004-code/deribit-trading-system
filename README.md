# deribit-trading-system

HI Myself Amit kumar a undergraduate student at IIITD and this is my given project for the deribit trading system it is a zip file but can download with the raw file easily.

Overview

Deribit Trading System is a high-performance order execution and management system that operates through a command-line interface. It uses a WebSocket client to connect to the Deribit TESTNET and manage trading portfolios with advanced functionality.


Features


WebSocket-based trading interface
Command-line trading operations
Support for various order types
API authentication
Open orders management
Order modification and cancellation
Tech Stack

C++ CMake WebSocket++ OpenSSL JSON Boost Readline

Prerequisites

System Requirements

C++ Compiler (g++)
CMake
Boost Libraries
OpenSSL
Git
Fast setup

To quickly configure your system and set up the project, please go ahead and execute the appropriate setup script for your operating system as detailed below.

NOTE: Please make sure you are in the repository's root directory before running the script.
macOS:

Run the following commands to execute the setup script:

chmod +x ./scripts/setup_mac.sh
./scripts/setup_mac.sh
Linux:

Run the following commands to execute the setup script:

chmod +x ./scripts/setup_linux.sh
./scripts/setup_linux.sh
Windows

For Windows, use the PowerShell script as follows:

Set-ExecutionPolicy Bypass -Scope Process -Force
.\scripts\setup_windows.ps1
This will install the necessary dependencies, build the project, and prepare it for use.

Installation Guide

Mac OS

Install Homebrew (if not already installed):
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
Install dependencies:
brew install cmake gcc boost openssl git readline
Linux (Ubuntu/Debian)

Update package list:
sudo apt update
Install dependencies:
sudo apt install cmake gcc libboost-all-dev libssl-dev git libreadline-dev
Windows

Download and Install:
CMake
Git
Visual Studio Build Tools
Boost Binaries
OpenSSL
Project Setup

Clone the Repository:
git clone https://github.com/Venkatesan-M/deribit-trading-system.git
cd deribit-trading-system
Create Build Directory:
mkdir build
cd build
Build the Project:
cmake .. -Wno-dev
cmake --build .
Run the Application:
./deribit_trader
Disclaimer

This is a trading system for educational and testing purposes. Always use caution and understand the risks involved in cryptocurrency trading.

Getting Started with Deribit

Account Setup

Create an account on Deribit Testnet


Generate API Keys:
Navigate to Account Settings
Create API Key
Set permissions (read/read_write)
Save Client ID and Client Secret securely
Application Usage

Basic Commands

help / man: Show all supported commands
quit / exit: Close WebSocket connections and exit
close <id> [code] [reason] : Closes the connection with the given id; optional: specify exit code and/or reason
connect <URI> : Creates a connection with the given URI
show <id>: Get connection metadata
send <id> msg: Send message to specific connection
show_messages <id>: View message exchanges
send <id> <message>: Sends the message to the specified connection
view_subscriptions: Displays the list of subscribed symbols to stream continuous orderbook updates
view_stream: Displays the stream continuous orderbook updates subscribed symbols
latency_report : Generates a latency report of the current session
reset_report : Delete's the data of the latency report of the current session
Deribit API Commands

Connection and Authentication

Connect to Testnet: Creates a new connection to the Deribit testnet website
Deribit connect
connect wss://test.deribit.com/ws/api/v2
Authenticate: Sends the authorization message to retrieve the access token; optional: use -s to remember the token for the session
Deribit <id> authorize <connection_id> <client_id> <client_secret> [-s]
Order Management

Buy Order: Places a buy order for the specified instrument
Deribit <id> buy <instrument> <transaction_name>
Sell Order: Places a sell order for the specified instrument
Deribit <id> sell <instrument> <transaction_name>
Modify Order: Modifies the price or amount of an active order
Deribit <id> modify <order_id>
Cancel Order: Cancels the specified order
Deribit <id> cancel <order_id>
Cancell all orders

Deribit <id> cancel_all
Information Retrieval

Get Open Orders: Fetches all open orders with optional filters
Deribit <id> get_open_orders [<currency>] [<instrument>] [<label>]
View Positions: Fetches all your current open positions; optional: use options to be specific
Deribit <id> positions [currency] [kind]
Get OrderBook: Fetches all current buy and sell orders for the specified instrument; optional: specify depth of search
Deribit <id> orderbook <instrument> [<depth>]
Symbol Subscription

Subscribe to a symbol: Subscribes to that symbol to stream continuous orderbook updates
Deribit <id> subscribe [symbol]
Unsubscribe to a symbol: Unsubscribes to that symbol to stream continuous orderbook updates
Deribit <id> unsubscribe [symbol]
Unsubscribe to all symbol: Unsubscribes to all symbols that have been subscribed to stream real time data
Deribit <id> unsubscribe_all
Supported Order Types

Order Type	Flag
Limit	limit
Stop Limit	stop_limit
Take Limit	take_limit
Market	market
Stop Market	stop_market
Take Market	take_market
Market Limit	market_limit
Trailing Stop	trailing_stop
Time in Force Options

Option	Flag
Good Till Cancelled	good_til_cancelled
Good Till Day	good_til_day
Fill or Kill	fill_or_kill
Immediate or Cancel	immediate_or_cancel
Project Structure

├── include # Header files
│   ├── api
│   │   └── api.h
│   ├── authentication
│   │   └── password.h
│   ├── json
│   │   └── json.hpp
│   ├── utils
│   │   └── utils.h 
│   └── latency
│       └── tracker.h
│   └── websocket
│       └── websocket_client.h
├── README.md
├── setup.sh
└── src
    ├── main.cpp # main function (deribit trader)
    ├── api
    │   └── api.cpp # Implementation Deribit API's Functionality
    ├── authentication
    │   └── password.cpp # Authentication and Session Management Functionality
    ├── latency
    │   └── tracker.cpp # Latenct tracking logic
    ├── utils
    │   └── utils.cpp # Helper functions and utils
    └── websocket
        └── websocket_client.cpp # websocketpp and WebSocket endpoint implementation
Development

image

you are free to develop more feature on this, just refer the new DERIBIT API DOCS
Test the API Call on Deribit API Console
Contribution

Contributions are welcome! Please follow these steps:

Fork the repository
Create a new branch
Make your changes
Submit a pull request
