# How it works

Now we'll go into the technical details of what happens behind the scenes which allows the users to own the underlying assets. Before that a quick graph to show why a new user would choose BIT10.

<table><thead><tr><th width="152">Strategy</th><th>Fees spent</th><th>Time spent</th><th>Risk/Return</th><th>Volatilty</th></tr></thead><tbody><tr><td>Crypto Picking</td><td>🔴 High</td><td>🔴 High</td><td>🟡 Medium</td><td>🔴 High</td></tr><tr><td>BIT10</td><td>🟢 Low</td><td>🟢 Low</td><td>🟢 Low</td><td>🟡 Medium</td></tr></tbody></table>

The back-end infrastructure for BIT1O is made possible with ICP's(Internet Computer Protocol), specifically their ICRC-1 standard. We can use it for many different things (linked below)\
[https://internetcomputer.org/docs/current/references/icrc1-standard](https://internetcomputer.org/docs/current/references/icrc1-standard)

The part we're interested in was the canister smart contracts and the capabilities that it gives us. A token canister implementing the ICRC-1 standard includes the necessary functions for managing token balances, transfers, and approvals. As well as that, Canisters can talk to other canisters which allows us to build a cohesive ecosystem of decentralized applications that can leverage each other's functionalities.

The first step was getting the price of the Token which required some real world data from an Oracle.\
In DeFi, oracles play a crucial role by providing external data to smart contracts. For BIT10, we used ICP's exchange rate canister and the Coinbase API to determine the current value of the BIT10 token, ensuring accurate and up-to-date data for our DApp.

**Using the ICP Exchange Rate Canister**

The ICP exchange rate canister is a service on the Internet Computer that provides exchange rates for various fiat currencies and cryptocurrencies. By integrating this canister into the oracle, we ensure that the BIT10 token's value is computed using reliable and accurate exchange rate data. The exchange rate canister offers several benefits: Accuracy: Real-time Data and Decentralization.

**Calculating the Bit10 Token Value**

With data from the ICP exchange rate canister and the Coinbase API, the oracle can perform the following steps to calculate BIT10 token's value:

1. Fetch Exchange Rates: Retrieve the latest exchange rates for relevant fiat currencies and cryptocurrencies from the ICP exchange rate canister.
2. Fetch Cryptocurrency Prices: Use the Coinbase API to get the current prices of the cryptocurrencies in the Bit10 index.
3. Compute Index Value: Calculate the Bit10 token's value by applying the weights of the constituent cryptocurrencies to their current prices and aggregating the results.

#### How the Collateralization Will Work

Collateralization is vital for the issuance and management of the BIT10.DeFi token. This ensures that for every BIT10.DeFi token purchased by a user, an equivalent value of the underlying assets is bought and securely stored. This approach guarantees the token’s value and provides confidence to investors that their holdings are backed by real assets.

**Overview of Collateralization**

Collateralization involves purchasing and holding the underlying assets that back a financial instrument. In the case of the BIT10.DeFi token, these underlying assets are various cryptocurrencies, in the BIT10.DEFI token such as Internet Computer Protocol (ICP), Stacks, Conflux, Map Protocol, RIF, and Sovryn. For each BIT10.DeFi token issued, a corresponding amount of these cryptocurrencies is acquired and stored in a secure and decentralized manner using the ICP canister.

**Step-by-Step Collateralization Process**

1. User Purchases BIT10.DeFi Token: they initiate a purchase transaction. This transaction specifies the number of BIT10.DeFi tokens the user wishes to buy.
2. Calculation of Underlying Assets: Upon receiving the purchase request, the system calculates the required amounts of each underlying cryptocurrency that make up the BIT10.DeFi token. The allocation is based on the predefined weights of the cryptocurrencies in the BIT10.DeFi index.\
   For example, the BIT10.DeFi index consists of equal parts of ICP, Stacks, Conflux, Map Protocol, RIF, and Sovryn, the system will calculate the exact amount of each token to be purchased for every BIT10.DeFi token bought.
3. Purchase of Underlying Assets: The system then proceeds to purchase the calculated amounts of each underlying cryptocurrency. This is done in real-time through integrated exchanges and liquidity providers.
4. Storage in ICP Canister: The purchased cryptocurrencies are securely stored in an ICP canister.  The ICP canister will hold the underlying assets, ensuring they are available to back the BIT10.DeFi tokens.
5. Issuance of BIT10.DeFi Tokens: Once the underlying assets have been successfully purchased and stored, the system issues the corresponding number of BIT10.DeFi tokens to the user. These tokens are now fully collateralized by the underlying assets held in the ICP canister.

**Ensuring Continuous Collateralization**

To maintain the value and trust in the BIT10.DeFi token, continuous monitoring and management of the collateralization process are done. This involves:

* Regular Audits: Conducting regular audits of the underlying assets held in the ICP canister to ensure they match the issued BIT10.DeFi tokens.
* Rebalancing: Periodically rebalancing the portfolio of underlying assets to align with any changes in the BIT10.DeFi index composition or market conditions.

Automated Monitoring: Implementing automated systems to monitor the value and security of the underlying assets, ensuring they are always adequately collateralized.

**How the Formula for the BIT10 Token Will Work**

The BIT10 token is designed to provide investors with a diversified exposure to a selection of cryptocurrencies. The value of the BIT10 token is determined by the average value of the underlying tokens that constitute the BIT10 index.&#x20;

Here’s how the formula works:

1\. Identify Constituent Tokens

The BIT10.DEFI index will consist of six cryptocurrencies(more for Mainet). These will be ICP, Stacks, Conflux, Map Protocol, RIF and Sovryn.

2\. Fetch Current Prices:

&#x20;The current prices of each of these tokens are fetched from reliable data sources such as the ICP exchange rate canister and the Coinbase API.&#x20;

3\. Calculate the Average Price

&#x20;The average price of the tokens is calculated by summing up the prices of all constituent tokens and then dividing by the number of tokens in the index. \
\
Example:&#x20;

\- ICP: $20

\- Stacks: $1

\- Conflux: $0.5

\- Map Protocol: $0.25

\- RIF: $0.75

\- Sovryn: $2

The average price calculation would be:

(20 + 1 + 0.5 + 0.25 + 0.75 + 2 )/6 = 4.08\
Thus, the value of one BIT10 token would be $4.08\
\
Benefits of the Average Price Method would the simplicity. It provides a straightforward way to calculate the BIT10 token value, making it easy for investors to understand. Diversification as averaging the prices of 6 different tokens, the BIT10 token offers diversified exposure.

To maintain the accuracy and relevance of the BIT10 token value, the prices of the  tokens are fetched and averaged in real-time or at regular intervals. Also periodic rebalancing of the index will be performed to reflect changes in the market or to replace tokens that no longer meet the criteria for inclusion in the index.
