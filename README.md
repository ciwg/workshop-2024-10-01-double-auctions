# Double Auctions: An Introduction

Community Systems Working Group

2024-10-01

---

# What is a Double Auction?

A double auction is a market mechanism where buyers and sellers declare orders to buy or sell an asset.

- **Example**: A street vendor and a tourist haggling over the price of a souvenir.

---

# Why double auctions matter

Double auctions perform **price discovery** -- the process of deciding a reasonable value for an asset.

Electronic double auctions are a modern global forum.  They
communicate need and availability of goods and services worldwide.
They are able to do this across national borders, languages, and
cultures, often reallocating resources within milliseconds of an
event.


---

# Double Auctions Govern Governments

A government's ability to function is ultimately limited by what the
bond market (a double auction) is willing to lend to the government's
treasury.

Bond traders lend money to a government by buying government bonds. For example:
- The US Treasury might wish to sell a bond that is worth $1000 in 10 years.  
- The US Treasury might try to sell this bond for $900 today.
- Whether the sale is successful depends on whether anyone is
  willing to buy the bond for $900 and accept the risk that the
  government might not repay the bond 10 years from now.

_"You mean to tell me that the success of the program and my reelection hinges on the Federal Reserve and a bunch of &#^%@ bond traders?" -- Bill Clinton_

- Whether between individuals or nations, double auctions are a key
  mechanism for decentralized governance.

---

# Key Features of Double Auctions

- **Buyers** submit orders to buy an asset
- **Sellers** submit orders to sell an asset
- A **Matching** process pairs buy and sell orders to **execute** trades.

---

# Limit Orders 

Double auctions are based on **limit orders**.

A limit order is an order to buy or sell an asset at a specified price or better.

- **Buy Limit Order**: Sets the maximum price at which you're willing to buy.
  - Also known as a "bid" or "buy"
  - We'll use "bid" in this presentation.
- **Sell Limit Order**: Sets the minimum price at which you're willing to sell.
  - Also known as an "ask", "offer", or "sell"
  - We'll use "ask" in this presentation.

---

# Limit Order examples

- **Bid Order**:
  - A proposal to buy a certain amount of an asset at a specified price.
  - Example: Buy 100 units at $5 each.
- **Ask Order**:
  - A proposal to sell a certain amount of an asset at a specified price.
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

**I promise to sell 50 units of XYZ at $10 each.**
- This means you are offering to sell a total of 50 units of XYZ for $10 each, expecting a total return of $500 if your ask is accepted.

In shorthand:

```
ASK 50 XYZ @10.00 USD
```

---

# Order Book

Buyers and sellers records each other's bids and asks in an **order book**.  This gives them a sense of the market's supply and demand.

Example of a simplified order book:

  | Type | Quantity | Asset | Price (USD) |
  |---|---|---|---|
  | ASK | 50 | XYZ | 10.00 |
  | ASK | 20 | XYZ | 9.00 |
  | ASK | 100 | XYZ | 6.50 |
  | BID | 100 | XYZ | 5.00 |
  | BID | 200 | XYZ | 4.50 |
  | BID | 150 | XYZ | 4.00 |


---

# Bid-Ask Spread

The bid-ask spread is the difference between the highest price a buyer is willing to pay (bid) and the lowest price a seller is willing to accept (ask).

Example: In this order book, the XYZ bid-ask spread is $1.50 (6.50 - 5.00).

  | Type | Quantity | Asset | Price (USD) |
  |---|---|---|---|
  | ASK | 50 | XYZ | 10.00 |
  | ASK | 20 | XYZ | 9.00 |
  | ASK | 100 | XYZ | 6.50 |
  | --- | --- | --- | --- |
  | BID | 100 | XYZ | 5.00 |
  | BID | 200 | XYZ | 4.50 |
  | BID | 150 | XYZ | 4.00 |


---

# Matching Engine

In an electronic trading system, the **matching engine** is a component that matches buy and sell orders from the order book.  

Example of a matching engine in action:

- A buyer submits a bid for 100 units of XYZ at $5 each.
- A seller submits an ask for 50 units of XYZ at $6.50 each.
- The matching engine does nothing -- the bid-ask spread is $1.50.
- Another seller submits an ask for 100 units of XYZ at $5 each.
- The matching engine pairs the buyer and new seller, executing a trade for 50 units of XYZ at $5 each.

Let's take that one step at a time on the next slides.

---

# How Double Auctions Are Used in Financial Markets

- **Stock Exchanges**:
  - Facilitate trading of financial instruments (e.g., stocks, bonds).
  - Ensure liquidity and fair price discovery through continuous double auctions.
- **Commodity Markets**:
  - Enable trading of commodities (e.g., oil, gold).
  - Align supply and demand dynamics of physical goods with market prices.

---

# How Double Auctions Are Used in Currency Exchange Trades

- **Currency Exchanges**:
  - Double auctions can facilitate the trading of various currencies.
  - Participants submit bids and asks in different currencies, enabling efficient currency exchange through transparent and competitive pricing.
  - Example: Traders exchanging USD for EUR or other fiat or cryptocurrencies.

---

# How Double Auctions Work in Peer-to-Peer Markets

- **Decentralized Markets**:
  - Peer-to-peer platforms where users can trade directly without intermediaries.
  - Double auctions help match buyers and sellers in these decentralized environments.
- **Advantages**:
  - Increased Market Efficiency: Direct matching leads to efficient price discovery.
  - Reduced Transaction Costs: Elimination of intermediaries reduces costs for participants.
  - Enhanced Privacy and Security: Use of cryptographic protocols ensures privacy and security.
  
---

# Implementing Double Auctions in a Decentralized System

- **Decentralized Matching Engine**:
  - Peer-to-peer network nodes work together to match buy and sell orders.
  - Ensures robustness and removes single points of failure.
- **Advantages**:
  - Resilience
  - Transparency
  - Efficiency in resource distribution
  - Enhanced trust among participants

---

# Tracking Multiple Local Microcurrencies and Resource Allocation

- **Microcurrencies**:
  - Digital tokens used within localized, decentralized systems.
  - Help quantify and manage local resources and services.
- **Resource Allocation**:
  - Double auctions can optimize the distribution of resources by matching supply and demand efficiently.
  - Example: Local communities trading solar energy credits.

---
