# Double Auctions: An Introduction

Community Systems Working Group

2024-10-01

---

# What is a Double Auction?

A double auction is a market mechanism where buyers and sellers declare orders to buy or sell an asset.

- **Example**: A street vendor and a tourist haggling over the price of a souvenir.

---

# Why Double Auctions Matter

Double auctions perform **price discovery** -- the process of deciding a reasonable value for an asset.

Electronic double auctions are a modern global forum. They communicate the need and availability of goods and services worldwide. They can do this across national borders, languages, and cultures, often reallocating resources within milliseconds of an event.

See "Wisdom of Crowds" by James Surowiecki for more on how markets can be more timely and accurate than single experts.

Also see:
- prediction markets, which are essentially double auctions for predicting future events.
- "The Future of Work" by Thomas Malone for more on how decentralized systems can be more efficient than centralized ones.
- Todd Proebsting's work at Microsoft Research on prediction markets.

---

# Double Auctions Govern Governments

A government's ability to function is ultimately limited by what the bond market (a double auction) is willing to lend to the government's treasury.

Bond traders lend money to a government by buying government bonds. For example:
- The US Treasury might wish to sell a bond now with a promise to buy it back for $1000 in 10 years.  
- They might try to sell this bond for $900 today.
- Whether the sale is successful depends on whether anyone is willing to buy the bond for $900 and accept the risk that the government might not fulfill the promise 10 years from now.

_"You mean to tell me that the success of the program and my reelection hinges on the Federal Reserve and a bunch of &#^%@ bond traders?" -- Bill Clinton_

- Whether between individuals or nations, double auctions are a key mechanism for decentralized governance.

---

# Key Features of Double Auctions

- **Buyers** submit orders to buy an asset.
- **Sellers** submit orders to sell an asset.
- A **Matching** process pairs buy and sell orders to **execute** trades.

---

# Limit Orders 

Double auctions are based on **limit orders**.

A limit order is an order to buy or sell an asset at a specified price or better.

**Buy Limit Order**: Sets the maximum price at which you're willing to buy.
- "I'll buy that car from you for $5000."
- Also known as a "bid" or "buy"
- We'll use "bid" in this presentation.

**Sell Limit Order**: Sets the minimum price at which you're willing to sell.
- "I'll sell that car to you for $6000."
- Also known as an "ask," "offer," or "sell"
- We'll use "ask" in this presentation.

---

# Limit Order Examples

- **Bid Order**:
  - A proposal to buy a certain quantity of an asset at a specified price.
  - Example: Buy 100 units at $5 each.
- **Ask Order**:
  - A proposal to sell a certain quantity of an asset at a specified price.
  - Example: Sell 100 units at $6 each.

---

# Example of a Bid Order 

**I promise to pay $5 each for 100 units of XYZ.**
- This means you are committing to spending a total of $500 to buy 100 units of XYZ if your bid is accepted by someone else.

In traders' shorthand, this might be written as:

```
BID 100 XYZ @5.00 USD
```

---

# Example of an Ask Order

**I promise to sell 100 units of XYZ at $6.50 each.**
- This means you are offering to sell a total of 100 units of XYZ for $6.50 each, expecting a total return of $650 if your ask is accepted.

In shorthand:

```
ASK 100 XYZ @6.50 USD
```

---

# Order Book

Buyers and sellers record each other's bids and asks in an **order book**. This gives them a sense of the market's supply and demand.

Example of a simplified order book:

  | Trader | Quantity XYZ | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 50           |         | 10.00   |
  | Alice  | 20           |         | 9.00    |
  | Bob    | 100          |         | 6.50    |
  | Alice  | 100          | 5.00    |         |
  | Carol  | 200          | 4.50    |         |
  | Bob    | 150          | 4.00    |         |

---

# Bid-Ask Spread

The bid-ask spread is the difference between the highest price a buyer is willing to pay (bid) and the lowest price a seller is willing to accept (ask).

Example: In this order book, the XYZ bid-ask spread is $1.50 (6.50 - 5.00).

  | Trader | Quantity XYZ | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 50           |         | 10.00   |
  | Alice  | 20           |         | 9.00    |
  | Bob    | 100          |         | 6.50    |
  | Alice  | 100          | 5.00    |         |
  | Carol  | 200          | 4.50    |         |
  | Bob    | 150          | 4.00    |         |

---

# Matching Engine

In an electronic trading system, the **matching engine** is a component that matches buy and sell orders from the order book.  

---

# Matching Engine in Action: Step 1

Here is our starting order book -- the bid-ask spread is $4.50 (9.00 - 4.50), so no trades are happening:

  | Trader | Quantity XYZ | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 50           |         | 10.00   |
  | Alice  | 20           |         | 9.00    |
  | Carol  | 200          | 4.50    |         |
  | Alice  | 150          | 4.00    |         |

A buyer (Bob) submits a bid for 100 units of XYZ at $5 each. The bid-ask spread is now $4 (9.00 - 5.00), still no trade:

  | Trader | Quantity XYZ | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 50           |         | 10.00   |
  | Alice  | 20           |         | 9.00    |
  | Bob    | 50          | 5.00    |         |
  | Carol  | 200          | 4.50    |         |
  | Alice  | 150          | 4.00    |         |

---

# Matching Engine in Action: Step 2

A seller (Alice) submits an ask for 50 units of XYZ at $6.50 each. The bid-ask spread is now $1.50, still no trade:

  | Trader | Quantity XYZ | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 50           |         | 10.00   |
  | Alice  | 20           |         | 9.00    |
  | Alice  | 50           |         | 6.50    |
  | Bob    | 50           | 5.00    |         |
  | Carol  | 200          | 4.50    |         |
  | Alice  | 150          | 4.00    |         |

---

# Matching Engine in Action: Step 3

Another seller (Carol) submits an ask for 100 units of XYZ at $5 each. The matching engine notices that the bid-ask spread is now $0:

  | Trader | Quantity XYZ | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 50           |         | 10.00   |
  | Alice  | 20           |         | 9.00    |
  | Alice  | 50           |         | 6.50    |
  | Carol  | 100          |         | 5.00    |
  | Bob    | 50          | 5.00    |         |
  | Carol  | 200          | 4.50    |         |
  | Alice  | 150          | 4.00    |         |

---

# Matching Engine in Action: Step 4

The matching engine now executes a trade between the buyer (Bob) and the seller (Carol) at $5 each for 50 units of XYZ, removing those 50 units from the order book. The remaining `ASK 50 @5.00` remain in the book, because no more bid orders match:

  | Trader | Quantity XYZ | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 50           |         | 10.00   |
  | Alice  | 20           |         | 9.00    |
  | Alice  | 50           |         | 6.50    |
  | Carol  | 50           |         | 5.00    |
  | Carol  | 200          | 4.50    |         |
  | Alice  | 150          | 4.00    |         |

---

# How Double Auctions Are Used in Currency Exchange Trades

There is no difference between trading currencies and trading other assets in a double auction. When trading two currencies, we choose one currency to be our "asset" and the other currency to be what we're using for our unit of exchange.

For example, if we want to buy 100 EUR by spending USD, and we think that the Euro is worth 1.10 USD, we submit a bid to buy 100 EUR at 1.10 USD each:

```
BID 100 EUR @1.10 USD
```

---

# Currency Exchange Order Book

This is what an order book might look like for a currency exchange. Here traders are buying and selling euros (EUR/USD) using US dollars (USD):

  | Trader | Quantity EUR | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 1000         |         | 1.30    |
  | Bob    | 2000         |         | 1.25    |
  | Alice  | 1500         |         | 1.20    |
  | Alice  | 2000         | 1.10    |         |
  | Carol  | 3000         | 1.05    |         |
  | Bob    | 4000         | 1.00    |         |

## Discussion:  Which Currency is Worth More?

In the above order book, which currency has higher value per unit, the USD or the EUR?

---

# Market Orders

A market order is an order to buy or sell an asset immediately at the best available current price.

- **Characteristics**:
  - Immediate Execution: No waiting for a matching order at a specific price.
  - Guaranteed Order Fulfillment: As long as there are willing buyers/sellers in the market.
  - No Price Guarantee: You get the next available price, which might fluctuate.

## Example:
  - If a buyer submits a market order to buy 100 units of XYZ, the order will be matched with any available sell orders (asks) on the order book. If the lowest ask price is $6.50, the market order will execute at that price.

```
BID 100 XYZ @MARKET  
```
...executes as:

```
BID 100 XYZ @6.50 USD
```

---

# Market Orders and the Order Book

Here is an order book. Consider the following questions:
1. What price will someone buy at if they submit a market bid order?
2. What price will someone sell at if they submit a market ask order?

  | Trader | Quantity XYZ | Bid USD | Ask USD |
  |--------|--------------|---------|---------|
  | Carol  | 50           |         | 10.00   |
  | Alice  | 20           |         | 9.00    |
  | Bob    | 100          |         | 6.50    |
  | Carol  | 100          | 5.00    |         |
  | Bob    | 200          | 4.50    |         |
  | Alice  | 150          | 4.00    |         |

Retail traders (consumers) often use market orders, unaware that they are essentially paying the bid-ask spread to the person on the other side of the trade.

---

# Market Makers: Income from Bid-Ask Spread

Market makers are participants who place limit orders at or inside the best bid and ask prices.

- **Income from Bid-Ask Spread**:
  - Market makers buy at the bid price and sell at the ask price.
  - The difference (spread) is their profit.
  - XXX mention risk
  
Example: 
- Buy 100 units at $5 each (total $500).
- Sell 100 units at $6.50 each (total $650).
- Profit: $150 ($650 - $500).

In most markets, **anyone can be a Market Maker**:
  - As long as the spread is wide enough to cover costs and provide a profit.
  - Costs include transaction fees, risk of price movement, and holding costs.

---

# Sidebar: Currency Exchange Booths

- When you trade with a currency exchange booth at an airport, you are using a **market order**, paying the spread.
- The booth acts as a **market maker**.
- The booth makes their income from the spread.

# Example: 

Let's look at an order book for a USD/MXN (US Dollar/Mexican Peso) exchange at an airport booth. The exchange rate midpoint is 19.69 with a 0.20 MXN spread.

  | Trader | Quantity USD | Bid MXN | Ask MXN |
  |--------|--------------|---------|---------|
  | Booth  | 1000         |         | 19.79   |
  | Booth  | 1000         | 19.59   |         |

- The booth is both the buyer and seller (market maker).
- You are buying or selling USD to the booth, in exchange for MXN.
- If you sell USD to the booth, you get 19.59 MXN/USD.
- If you buy USD from the booth, you pay 19.79 MXN/USD.
- The booth's profit is the spread (0.20 MXN per USD).

# Discussion: 

- How much USD will you be left with if you sell $1000 USD for MXN, and then buy the USD back with the MXN you received?

---

- answer: $980 USD ?

---

# Implementing Double Auctions in a Decentralized System

- Peer-to-peer network nodes work together to match buy and sell orders.
- Ensures robustness and removes single points of failure.

But making this work requires either:

- Peers trusting each other to agree on the order book and matching trades.
- A third-party matching engine that both peers trust.
- A blockchain-based system that ensures trust and transparency via decentralized consensus.
  - proof-of-work (e.g. Bitcoin), proof-of-stake (e.g. Ethereum), or other consensus mechanisms.
- Some other mechanism: e.g. multi-party computation, zero-knowledge proofs.

---

# Personal Currencies 

"Everyone is their own central bank." 

Personal currencies act as both a reputation system and a way to trade
and allocate resources.

- Microcurrencies?
- Nanocurrencies?

- "Why You Should Be Able to Make Your Own Individualized, Digital
  Nano-Currency"
  https://mags.acm.org/communications/august_2023/MobilePagedArticle.action?articleId=1897744#articleId1897744 

 

---

# Segue to PromiseGrid

- It's looking like PG uses a double auction mechanism to trade personal currencies.
- Relative value of personal currencies is determined by the double auction.
- Reputation is built by fulfilling promises.
- Reputation is relative -- equivalent to the value of the personal currency. 

---

