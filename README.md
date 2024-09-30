# Double Auctions: An Introduction

Community Systems Working Group

2024-10-01

---

# What is a Double Auction?

- **Definition**: A double auction is a market mechanism where multiple buyers and sellers submit bids and asks simultaneously.
- **Bid**: An offer to buy a specific quantity of an asset at a given price in a given currency.
- **Ask**: An offer to sell a specific quantity of an asset at a given price in a given currency.
- **Objective**: To discover the equilibrium price at which the quantity of goods demanded equals the quantity supplied.

---

# What is a Bid or Ask Order?

- **Bid Order**:
  - A proposal to buy a certain amount of an asset at a specified price.
  - Example: Buy 100 units at $5 each.
- **Ask Order**:
  - A proposal to sell a certain amount of an asset at a specified price.
  - Example: Sell 100 units at $6 each.

---

# Example of a Bid Order in Ledger-CLI Format

**I promise to pay $5 each for 100 units of XYZ.**
- This means you are committing to spending a total of $500 to buy 100 units of XYZ if your bid is accepted by someone else.

```
2024/10/01 (PENDING) Buy 100 units of XYZ at $50 each
    Assets:Margin       $500.00
    Assets:Cash          -$500.00
```

- **Margin**:
  - **What is Margin?**
    - Margin is the collateral or funds you set aside to support your bid. It ensures that you have sufficient resources to follow through if your bid is successful.
  
- **Understanding the Margin Entry**:
  - In the transaction above, $500 is moved from your **Assets:Cash** account to your **Assets:Margin** account. This action reserves the funds, ensuring they are available to complete the purchase if your bid is matched.

---

# Example of an Ask Order in Ledger-CLI Format

**I promise to sell 50 units of XYZ at $10 each.**
- This means you are offering to sell a total of 50 units of XYZ for $10 each, expecting a total return of $500 if your ask is accepted.

```
2024/10/01 (PENDING) Sell 50 units of XYZ at $10 each
    Assets:Inventory:-50 XYZ
    Income:Sales       $500.00
```

- **Inventory**:
  - **What is Inventory?**
    - Inventory here represents your stock of the item you are willing to sell.
  
- **Understanding the Inventory Entry**:
  - In the transaction above, 50 units are moved out from your **Assets:Inventory** account, and $500 is moved into your **Income:Sales** account. This action signifies the sale, ensuring your inventory and revenue are accurately represented.

---

# What is an Order Book?

- **Order Book**:
  - A real-time, continuously updated list of buy and sell orders in the market.
  - Contains:
    - **Buy Orders (Bids)**: Listed from highest to lowest price.
    - **Sell Orders (Asks)**: Listed from lowest to highest price.
  - **Purpose**: To display current supply and demand, facilitating transparency and price discovery.

---

# What is a Matching Engine?

- **Matching Engine**:
  - A system component that matches buy and sell orders from the order book.
  - **Algorithm**: Matches highest bid with the lowest ask to execute a trade.
  - **Functions**:
    - Ensures trades are executed fairly and efficiently.
    - Updates the order book in real time.

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
