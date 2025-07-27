# zeru
"Risk scoring system for Ethereum wallets using Compound V2/V3 transaction data."
# Wallet Risk Scoring

## Overview
This project evaluates the risk profile of Ethereum wallets using transaction data from Compound V2/V3 protocols. Each wallet is assigned a risk score between **0 and 1000**.

---

## Data Collection Method
Transaction data was retrieved using the Covalent API for the provided wallet list. Each transaction includes details like gas spent, fees paid, and timestamps.

---

## Feature Selection Rationale
Key features were selected to reflect on-chain risk behavior:
- **Fees Paid** – High fees may indicate frequent trading or high-value interactions.
- **Gas Spent** – Reflects transaction complexity and frequency.
- **Transaction Count** – Measures activity level.

---

## Scoring Method
1. Features were normalized using **MinMaxScaler**.
2. Weighted formula applied:  
   - 50% weight to Fees Paid  
   - 30% weight to Gas Spent  
   - 20% weight to Transaction Count  
3. Final score scaled to a 0–1000 range.

---

## Justification of Risk Indicators
- **Fees and Gas**: High values may imply risky trading patterns or heavy leverage.
- **Transaction Count**: Identifies highly active wallets, which may have higher exposure.

---

## Output
- `wallet_risk_scores.csv` containing:
