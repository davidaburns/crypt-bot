# Data Models
When thinking about a bot that can implement trading strategies and execute trades on your behalf we need to map out some data/models
that the bot will interact with

## Market
- The market represents the countries stock exchange
- Some markets can be traded on a global level

## Exchanges
- An exchange is where trades of stocks, commodities, options, and crypto happen
- There are multiple different exchanges with various fees and different prices
- In order for a bot to interact with an exchange there must be an accessible API either open or premium based
- Data Needed
  - Exchange name
  - Login (optional based on how one interfaces with the exchange)
  - API tokens 
  - Data method (HTTP vs Websocket)
  - Polling Rate (Rate at which data will be retrieved from the exchange in regards to prices, equity, portfolio, etc)
  - Exchange specific config data (This could be any exchange specific config that is needed to interact with the exchange through its APIs)


## Symbols
- A symbol represents the actual stock,option,crypto,etc
- This is required in order to retrieve data from the exchange, the same symbol will be used across all exchanges
- Data Needed
  - Symbol name
  - Current Price
  - Last Change Price
  - Last Change Percentage
  - Current Market Cap
  - Last Updated (Timestamp)
  - Historical Data (Market Data)
  - Historical data will be cached and only pulled once per symbol over the past 5 years in single day intervals
    - Open Price
    - Close Price
    - Average Price
    - High Price
    - Low Price
    - Volume Traded
  - Current 24hr Prices (Midnight to Midnight)
    - Represents the current day price changes
  - Globally Traded?
    - Is this stock/crypto globally traded or in a specific market?
  - Trade Strategy
    - A list of strategies to be used to determine the behavior of trades for this symbol
  - Current Trend
    - Is the price of this symbol trending upwards, downwards, or maintaining over time
  - Strategy Execution Rate
    - The rate at which the configured strategies for this symbol will run

## User Profile
- A profile that houses user data
- Data Needed
  - Exchanges
    - A list of exchanges and their respective data need
  - Currency Used
    - The currency that will be used to calculate trades
  - Portfolio
    - Symbols
    - Total Equity
    - Historical Equity Points
      - A list of points where your 
  - Wallet
    - Trade Amount
      - The amount of money out of total money that is able to be traded (Precent vs specific amount)
    - Unavailable Amount
      - The amount of money that is currently unavailble to trade (Considered Profit?)
    - Fee Amount
      - The amount of money that will be set aside to cover cost of fees for trades

## Trade Strategy
- A set of rules and behaviors that make up a strategy on how to trade your stocks
- Market data trends, current price info, etc will be pumped through the strategy and output the suggested action to take
  - BUY (Symbol, Quantity, Price, When)
  - SELL (Symbol, Quantity, Price, When)
  - HOLD