# USX - 2024.6

# **Overview**

## **Introduction**

USX is an over-collateralized stablecoin implementing multiple minting modules including global-pool, vault, and LSR. USX's dollar peg is mainly dictated by a hybrid interest policy that can efficiently improves USX's liquidity on secondary market by adjusting its lending and borrowing rates on supported protocols. Powered by the LSR module, USX is also 1:1 tradable with other supported stablecoins directly through dForce Trade.

Stablecoin is the Holy Grail of crypto. Decentralized stablecoin experiments have gained strong momentum with comprehensive iteration of mechanism and tokenomics. Today, stablecoins have seen huge adoption over other crypto assets, and will eventually evolve into a multi-trillion-dollar market.

With centralized stablecoins dominating the market, a great number of decentralized stablecoins have been making robust growth in market cap and user adoptions over the past year.

dForce has embarked on our stablecoin and DeFi journey since late 2019, from the first pilot meta-stablecoin USDx to the over-collateralized stablecoin USX. We believe there are several necessary conditions for a decentralized stablecoin to become successful, mainly the price peg and expansion of user cases beyond self-incentivizing.

### Features

USX is the most important DeFi primitive within the dForce’s protocol matrix, starting off with an over-collateralization design, where supported assets can be used as collaterals to mint USX within the respective approved LTV ratio (similar to DAI). However, USX distinguished itself from other over-collateralized stablecoins in several aspects:

- **Flexible and efficient minting models.** USX can be minted through 1) Vault (single collateral & risk-isolated); 2) borrowing from supported lending protocols (pool-based & multi-collateral & market-driven rates) directly; 3) 1:1 swap with supported stablecoins (LSR).
- **Omni-yield stablecoin:** [sUSX](notion://www.notion.so/o/GMMGZtcjnsbTNrgU56TC/s/8Qz6Wp9AI1XXGRr73nr8/~/changes/8/susx) implements a unified and consistent yield generation mechanism across multiple blockchain networks. This means that users can earn saving rates on their assets uniformly, regardless of which blockchain they are using.
- **Protocol controlled liquidity** to support scenarios covering credit granting and multiple use cases. This feature is particularly useful to facilitate protocol-to-protocol interactions, i.e., to seed liquidity into USX bridges and stablecoin swap pools.
- **A hybrid interest rate policy.** USX can be minted with 1) fixed interest rates under the Vaults model. Different collaterals can enforce different interest rates through multiple Vaults, adjustable through governance voting. 2) range-bound market interest rate powered by the PDLP (Protocol-Direct-Liquidity-Provision) module through controlling USX's supply in the secondary market.
- **LSR (Liquid Stability Reserve) module** enables 1:1 swap between USX and a number of supported stablecoins, allowing arbitragers to bypass marketing slippage with 0% fees for minting and redeeming USX on dForce. It plays an important role in keeping USX pegged 1:1 with the US dollar.
- **Multichain liquidity conduit.** USX can be minted natively on all deployed chains, with cross-chain-enabled liquidity capability. This positions USX as the only stablecoin that can serve as a cross-chain bridge with liquidity guarantee (powered by the PDLP module), allowing users to move USX across supported chains with zero slippage and uncapped limit. Stacked with Swap and Lending, users can move any crypto assets across different chains with zero slippage and minimized liquidity cap (only subject to USX’s liquidity on destination chain). For example, if you swap asset A to USX on Chain X, bridge USX to Chain Y and swap it back to asset A, you won’t be capped by bridge liquidity – this is completely untenable to fiat-back stablecoins like USDC, USDT, etc.
- **Decentralization.** USX is 100% decentralized with DF holders governing the protocol, including but not limited to parameter setting, liquidity operation, onboarding of new collaterals, new feature implementation, etc.

### **How to Get USX?**

USX is supported on a number of DEXes on different blockchains and L2s:

- Ethereum: [Curve](https://arbitrum.curve.fi/factory/13), [Uniswap V3](https://app.uniswap.org/#/swap?chain=mainnet)
- Arbitrum: [Camelot](https://app.camelot.exchange/), [Balancer](https://app.balancer.fi/#/arbitrum/swap), [Curve](https://arbitrum.curve.fi/factory/13), [Uniswap V3](https://app.uniswap.org/#/swap?chain=arbitrum)
- BSC: [DODO](https://app.dodoex.io/), [Pancake](https://pancakeswap.finance/swap)
- Optimism: [Velodrome](https://app.velodrome.finance/swap)
- Base: [Aerodrome](https://aerodrome.finance/swap?from=0xc142171b138db17a1b7cb999c44526094a4dae05&to=0x833589fcd6edb6e08f4c7c32d4f71b54bda02913)

## **FAQ**

### **What is LSR?**

LSR is short for “Liquid Stability Reserve”. dForce community has approved the implementation of LSR as per [DIP027](https://snapshot.org/#/dforcenet.eth/proposal/0x237aa8812670859707f34947b3ec1e8c844cdbc849d275690ef79346660f49e6), serving the purpose of further stabilizing the peg of USX, improving capital efficiency.

### **How does the LSR work?**

The LSR facilitates a 1:1 minting and redemption process for USX using USDC, USDT, and DAI.

LSR is a stability module of USX, allowing users to use USDC, USDT, and DAI to 1:1 mint USX and redeem for reserve stablecoins. Reserve stablecoins will be automatically supplied to Unitus Finance, which can be lent out to earn interest - this mechanism ensures that USX minted through the LSR module are always over-collateralized.

Users should treat the LSR as a stable swap, which keeps buying and selling USX exactly the same amount in USDC, USDT, and DAI. Having that said, there is no guarantee you can redeem USX back to the same stablecoin you used to mint USX, because anyone can use the LSR to trade USX against different stablecoins, including those who minted USX from dForce Lending or dForce Vaults.

But all USX outstanding are always over-collateralized.

### **How much do you charge for using LSR?**

We don’t charge any fees for minting USX from other supported stablecoins; however, there will be a 0.1% fee applied for each redemption of USX for other supported stablecoins.

### **How much USX can I mint using LSR？**

The LSR module implements a ***Debt Ceiling*** for each reserve stablecoin, representing the maximum amount of USX that can be minted using the selected stablecoin as collateral (please note it may vary on different networks).

### **Can I redeem USX for the same reserve stablecoin?**

Redeeming USX via LSR will be subject to the availability of ***Reserves*** (total liquidity supplied to dForce Lending) and ***Liquidity*** (total liquidity - some stablecoin supplied might by utilised by the lending protocol).

That being said, there is no guarantee that you can redeem USX for the same stablecoin you used to mint USX. But you can redeem for other stablecoins as long as there is adequate liquidity. Alternatively, you can sell USX on supported DEXes directly (may incur slippage).

This mechanism will make arbitrage super efficient (i.e. sell USX for other stablecoins when the price is higher than $1, and vice versa), which can help USX restore its peg in the shortest possible time.

### **Why stable reserves don’t match the USX’s circulating supply? Is USX fully collateralized?**

Yes, USX is always fully collateralized. There are 3 ways to mint USX on dForce:

- Supply collateral assets with Collateral Ratio > 100% to mint (borrow) USX on dForce Lending;
- Supply collateral assets with Collateral Ratio > 100% to mint (borrow) USX on dForce Vaults;
- Use other stablecoins to 1:1 mint USX via the LSR module.

In many cases, users who mint (borrow) USX from dForce Lending or dForce Vaults, may redeem USX for other stablecoins through the LSR module directly to facilitate different trading/investment strategies, which shall also consume the LSR stablecoin reserves.

But these transactions doesn’t impact the over-collateralization of USX.

### **How can I redeem my USX when stable reserves in LSR are dried up?**

You can always sell USX for other stablecoins on the open market!

We have also partnered with multiple DEXes on different L1/L2 chains to further improve USX’s liquidity.

## **Resources**

- [Website](https://dforce.network/)
- [X](https://twitter.com/dForcenet)
- [Telegram](https://t.me/dforcenet)
- [Discord](https://discord.com/invite/c2PC8SM)
- [BLOG](https://medium.com/dforcenet)
- [Forum](https://forum.dforce.network/)

## **Contracts**

| Network | Contract Address |
| --- | --- |
| Ethereum | 0x0a5E677a6A24b2F1A2Bf4F3bFfC443231d2fDEc8 |
| Arbitrum | 0x641441c631e2F909700d2f41FD87F0aA6A6b4EDb |
| Optimism | 0xbfD291DA8A403DAAF7e5E9DC1ec0aCEaCd4848B9 |
| Base | 0xc142171b138db17a1b7cb999c44526094a4dae05 |
| BNB Chain | 0xB5102CeE1528Ce2C760893034A4603663495fD72 |
| Polygon | 0xCf66EB3D546F0415b368d98A95EAF56DeD7aA752 |
| Conflux | 0x422a86f57b6b6F1e557d406331c25EEeD075E7aA |
| zkSync | 0xdb89D7b0Dccd0C0e5aC3571133A9aa1a037945cb |

# Price Stability

USX is designed to maintain a 1:1 soft peg with the U.S. dollar. Its pegging mechanism is mainly dictated by the LSR (Liquid Stability Reserve) module. The idea is simple: make USX tradable 1:1 with other supported stablecoins directly.

Instead of borrowing USX from lending protocols with a fee or incurring price slippage on every trade, the LSR module allows arbitragers to depositing USX to dForce to withdraw supported stablecoins slippage-free, or vice versa, depositing supported stablecoins to dForce to mint USX at zero cost, depending on whether USX is below or above peg.

In addition to LSR, USX also features a hybrid interest rate policy that algorithmically adjusts to maintain market supply and demand equilibrium.

There are mainly two ways for DF holders to set the interest rates for USX:

1. 1.collectively vote to decide the interest rate for Vaults, which is a fixed interest rate adjustable through governance.
2. 2.guide USX’s interest rate on secondary market through a dynamic supply mechanism powered by PDLP module.

For example, in the event of a high demand for USX when the price is pushed above $1, we could either lower interest rates for the Vaults, making it less expensive to mint USX, or increase USX supply on lending protocols via PDLP. Both can help the price of USX return to $1 by increasing USX’s supply in the open market.

In contrast, when market demands shrink and the trading price of USX falls below $1, we could either increase interest rates for the Vaults, making it more expensive to mint USX and encouraging earlier repayment, or remove USX liquidity from lending protocol via PDLP. Both can help to reduce USX supply and push its price back to $1.

# **Minting & Redeeming**

## **LSR**

### **What is LSR?**

The LSR ***(Liquid Stability Reserve)*** module allows users to use supported stablecoins including USDC, USDT, and DAI as collaterals to mint USX (or redeem USX for supported stablecoins) at 1:1 rate. The launch of LSR was approved through [DIP027](https://snapshot.org/#/dforcenet.eth/proposal/0x237aa8812670859707f34947b3ec1e8c844cdbc849d275690ef79346660f49e6).

LSR is an improved version of Maker’s PSM ***(Peg Stability Module)***, with all stablecoins collected from LSR being deposited into dForce Lending to earn yield, unlocking a new revenue stream for dForce Treasury.

### **Benefits**

LSR is designed to help USX maintain its dollar peg in a more efficient manner:

Users can 1: 1 mint USX against supported collateral stablecoins (USDC, USDT, DAI).

Each collateral stablecoin carries a ‘Minting Cap’ to back the issuance of USX, translating to the total amount of USX that can be minted against each collateral stablecoin. Click [here](https://forum.dforce.network/t/dip027-proposal-to-launch-the-lsr-liquid-stability-reserve-module-for-usx/957) to view the minting cap for each collateral stablecoin supported.

All stablecoin reserves collected from the LSR module will be automatically deposited into lending protocols (i.e., dForce Lending, Aave, etc) to earn yields, unlocking a new revenue stream for dForce Treasury.

Since most stablecoin reserves will be supplied to lending protocols to earn yield, if the LSR pool doesn’t have a sufficient balance to support redemption, users can still sell USX on supported DEXes.

### **Fees**

We don’t charge any fees for minting USX from other supported stablecoins; however, there will be a 0.1% fee applied for each redemption of USX for other supported stablecoins.

## **Pool**

### Over Collateralization

Users can borrow (mint) USX by depositing other supported assets to lending protocols (such as Unitus Finance) as collateral. 

The value of the collateral assets must be higher than the value of USX borrowed. If the value of the collateral drops below a certain threshold (borrowers must maintain an adequacy ratio greater than 1 on Unitus Finance to keep their positions safe from liquidation), the collateral is automatically sold to maintain the stability of USX.

### **Range-Bound Rates**

Pool-based minting is facilitated by the PDLP (Protocol-Direct-Liquidity-Provision) module, enabling supported lending protocols to utilize USX's yield tokens (i.e., iUSX) as collateral to mint USX.

The PDLP mechanism algorithmically allocates USX liquidity to supported lending protocols by accepting USX's yield tokens as collateral. USX will always remain over-collateralized, as the value of yield tokens accrues over time.

The borrow interest rate for USX will be anchored within a capped range and determined by USX's utilization rate. For instance, if the target borrow interest rate for USX is set at 3%, and market demand drives the borrow interest rate above 3%, additional USX liquidity will be provided to lending protocols via PDLP to lower the utilization rate. This ensures that the borrow interest rate remains within the specified range (equal to or less than 3%). Conversely, when market demand decreases, USX liquidity will be withdrawn from lending protocols, leading to an increase in utilization and interest rates.

### **Benefits**

The pool-based model carries the following competitive advantages:

It greatly improves capital efficiency by providing USX liquidity to lending protocols directly, which doesn't require users to mint USX and supply in the secondary market.

Market-driven interest rate is more adaptive and flexible, serving as a great supplement to the Vault-based fixed interest rate model.

It further extends collateral support for USX to a wider range of assets.

### **Whitelisted Lending Protocols**

USX is a standard ERC-20 token that can be easily integrated with DeFi lending protocols, seamlessly and permissionlessly. However, the decision to add a lending protocol supporting USX to the whitelist, and activate the PDLP module, will be determined by a vote by the dForce DAO.

## **Vault**

### **What is dForce Vault?**

The dForce Vault is tailored to enhance capital efficiency for our users by broadening the spectrum of collateral types accepted for USX. It introduces a new dimension of flexibility and accessibility, enabling USX minting against a wide range of isolated collateral assets, each with its own distinct risk profile. This approach allows users to maximize their borrowing power while maintaining stringent risk management protocols.

Vaults can be tailored to support various collaterals in isolation, including interest-bearing tokens (such as iTokens, aTokens, etc.), LP tokens, LSD assets (such as wstETH, rETH, etc.), DeFi staking tokens (such as veDF, etc.), and other long-tail tokens.

Each vault will implement different risk parameters based on the assessment results for the specific collateral asset supported, including:

- Interest (borrowing APY)
- Debt Cap (USX cap for the Vault)
- Supply Cap (cap on collateral)
- LTV (loan to collateral ratio)
- Liquidation Fee (liquidation discount on the collateral given to liquidators)
- Borrow Fee (upfront fee for each borrowing)

Compared with the Pool-based model, the Vault-based model better accommodates long-tail assets (e.g., LP tokens) with an isolated risk model (e.g., implementing debt and borrow caps simultaneously) serving as a safeguard. It also features a fixed interest rate, whereas the Pool-based model implements market-driven rates.

Below are some examples of dForce Vaults supported:

### **LP Token Vault**

The LP Token Vault has been established to support LP tokens of USX-related pairs on several DEXes. This benefits both LPs and the protocol. LPs can achieve leverage of up to 20x over USX stablecoin pairs, enhancing capital efficiency. Additionally, increased liquidity will boost demand for USX in the open market and reduce liquidity subsidies for the protocol.

LP Token Vault was approved through [DIP024](https://snapshot.org/#/dforcenet.eth/proposal/0xc22c1c5b1f25cf658d28b8194bb3931bba49200f636d96464521ee60505c1c87).

| Blockchain | DEX | LP Token | USX Cap | LTV | Interest | Upfront Fee | Liquidation Fee |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Ethereum | Curve | USX/3CRV LP | 10,000,000 | 92% | 0.5% | 0.01% | 4% |
| Arbitrum | Curve | USX/2CRV LP | 10,000,000 | 92% | 0.5% | 0.01% | 4% |

### **LSD Vault**

The LSD Vault was introduced to improve capital efficiency for LSD holders, enabling them to maximize their DeFi gains alongside staking yields. The first of such Vaults is the wstETH Vault, where users can supply wstETH as collateral to mint USX and participate in other DeFi activities for higher returns.

The wstETH Vault was approved through [DIP034](https://snapshot.org/#/dforcenet.eth/proposal/0x5bbad4a4fade42b779ce5bab561fb889fe80872425a3b651090894cb0ebaf5ce) and and saETH through [DIP065](https://snapshot.org/#/dforcenet.eth/proposal/0x2b8202433684dc17d46ed916941430315f85897b719920819db4c1df12a31ce3).

| Blockchain | LSD | Supply Cap | Debt Ceiling | LTV | Interest | Upfront Fee | Liquidation Fee |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Arbitrum | wstETH | 20,000 wstETH | 3,000,000 USX | 82.5% | 16.0% | 0.00% | 4% |
| Arbitrum | saETH | 2,000 saETH | 4,000,000 USX | 70.0% | 16.0% | 0.00% | 5% |
| Optimism | wstETH | 20,000 wstETH | 3,000,000 USX | 82.5% | 16.0% | 0.00% | 4% |

# **Liquidity Modules**

Protocol controlled liquidity is a module that allows the protocol to own and control the majority of protocol and treasury assets (i.e., USX, DF, etc) in the open market. It offers several advantages:

- Maximize liquidity and improve capital efficiency - it combats liquidity shortage of USX effectively by adding or removing protocol owned liquidity in response to market demands.
- Significantly reduce DF inflation by cutting off subsidies on rented liquidity.
- Now the protocol owns the majority of DF liquidity in DEXes (i.e., DF/USX pairs), which helps the protocol to generate more revenue from LP fees.

## PDLP

### **Exploring PDLP**

PDLP is short for *Protocol-Direct-Liquidity-Provision* and was approved through [DIP019](https://forum.dforce.network/t/dip019-proposal-for-the-implementation-of-pdlp-and-poo/751). It is designed to combat liquidity shortage on secondary venues effectively with direct liquidity provision into secondary market.

USX is a hybrid decentralized stablecoin, under the Vault model, users supply collaterals to the Vaults to mint USX. This is the primary market to generate USX liquidity. MakerDAO used to 100% rely on the vault model for DAI's issuance.

The obvious drawback of primary issuance is capital inefficiency. For example, in order to provide USX (or DAI) liquidity to secondary market (i.e., lending or DEX), you have to 1) provide collateral to mint USX (or DAI); 2) supply minted USX (or DAI) to lending protocol to provide liquidity. In most cases, those who mint stablecoins in the primary market (vaults) do not have the incentive to provide liquidity in the secondary market.

The PDLP module allows the protocol to use USX‘s deposit certificates in lending protocols (i.e., iToken, aToken, cToken) as collateral to mint USX and supply the liquidity to lending protocols. That being said, minting USX and providing liquidity will be performed in one step - it removes the middleman (primary market issuers) and becomes an effective liquidity provider in the secondary market, making it highly efficient and market-driven.

For example, high market demand will drive up interest rates and trigger more supply of USX into the secondary market. On the contrary, previously added liquidity will be withdrawn when market demand drops, bringing the interest rates back to the target level.

PDLP is highly scalable and is able to accommodate a broad range of protocols, facilitating the expansion of USX liquidity across lending markets, DEXes, bridges and chains.

### **PDLP Strategies**

PDLP will mainly focus on principal-safe strategies to power USX liquidity across lending, bridges, and stablecoin swaps that are less exposed to impermanent loss.

**Lending**

Similar to the D3M model MakerDAO deployed with Aave, USX and EUX can be minted against USX or EUX's yield tokens in lending protocols (i.e., aToken of Aave or cToken of Compound) and directly deposit back to whitelisted protocols to provide liquidity (approved through [DIP019](https://snapshot.org/#/dforcenet.eth/proposal/0x667b6096f265f027b617b5f038c4cbd61650c710584fd843cc93d99706a0abf0)).

For example, when PDLP module issues USX liquidity to dForce Lending, it will take iUSX (interest token of dForce Lending) as collateral to secure the minting of USX.

When a user borrows USX from dForce Lending, he is required to provide collateral assets satisfying the predetermined LTV ratio to secure his USX loan, meaning that USX loans are always over-collateralized.

PDLP will enforce a range-bound borrow rate for USX, which is driven by USX's utilization rate across supported lending protocols. Whenever the borrow rate goes above the capped borrow rate, additional supply of USX will be deposited into the lending protocol to bring the borrow rate back to the bound range.

PDLP can support third-party lending protocols like Aave or Compound, subject to DF governance approval.

**Bridges**

Similar to lending protocols, PDLP can power whitelisted bridges with a pegged mechanism (i.e., Celer's cBridge). USX can be minted against deposit certificates of whitelisted bridges via PDLP (approved through [DIP021](https://snapshot.org/#/dforcenet.eth/proposal/0xfab7093f002a45cc781a2f7ef199ca127bdebd54faa2e6670bb83911a2e743a8)).

This operation aims to facilitate the bridging of USX across supported networks with zero or near-zero slippage, without capped liquidity.

Combined use of dForce bridge with swaps on destination chains, enable USX to serve as a universal liquidity token to facilitate the cross-chain bridging of any assets. For example, you can supply USDC to borrow USX on Arbitrum, use the bridge to bring USX to Optimism, supply USX as collateral to borrow USDC on Optimism. By doing so, you can bridge your ETH, BTC, etc to destination chains at affordable cost with minimized slippage.

**Swaps**

PDLP can also power stablecoin swaps paired with USX (i.e., USDC/USD, USX+3pool, etc), which are less exposed to impermanent loss (approved through [DIP019](https://snapshot.org/#/dforcenet.eth/proposal/0x667b6096f265f027b617b5f038c4cbd61650c710584fd843cc93d99706a0abf0)).

PDLP will use LP token, a representation of liquidity position in whitelisted DEXes, as collateral to mint USX. This mechanism will allow dForce to own liquidity and earn most of the LP fees for DF holders.

### **PDLP Limits**

Total assets controlled under PDLP will be allocated across different layers and blockchains (approved through [DIP021](https://snapshot.org/#/dforcenet.eth/proposal/0xfab7093f002a45cc781a2f7ef199ca127bdebd54faa2e6670bb83911a2e743a8)).

A total of 300m USX have been allocated to the broader Ethereum ecosystem. Minting will take place on Ethereum, but can be bridged to L2 solutions, including Arbitrum, Optimism, and more, within the limits.

200m USX have been allocated to BSC whilst USX will be minted natively on BSC via PDLP.

### **Whitelisted Protocols**

Approved PDLP limits are applicable to protocols listed below across all networks (including future deployment on other blockchains and layers):

- [dForce Protocols](https://app.dforce.network/)
- [Unitus Finance](https://unitus.finance/#/)
- [Celer's cBridge](https://cbridge.celer.network/#/transfer)

Other venues would need to seek additional approval from the dForce community through governance.

## POO

### **Exploring POO**

POO (*Protocol-Owned Operator*) is an improved version of PCV (*Protocol-Controlled-Value*), where dForce leverages treasury assets to mint USX and EUX, exchange them for the relevant paired asset or pair them with the relevant assets (i.e., USX/DF, EUX/USX), gradually acquiring and controlling most of dForce liquidity in the open market. This helps to reduce liquidity mining subsidies and allow the protocol to earn most of LP fees associated with protocol assets.

POO can also be combined with PDLP to generate yield from multiple sources for DF holders, increase organic use as well as protocol revenues through yield-carrying trades.

### **How does it work?**

With PDLP tackling the liquidity problem, POO will focus on enhancement of capital efficiency as well as yield and revenue generation capability. POO will initially fulfill the following functionalities:

- Provide liquidity to AMM pools for dForce assets (USX/DF, EUX/DF, USX/EUX, etc), building a sustainable path that will eventually remove liquidity mining subsidies.
- Borrow directly from the protocol to earn a return via carry-trades (i.e., borrow ETH and convert to wstETH to earn staking yield).
- Facilitate integration with a broader range of DeFi protocols (i.e., provide bootstrapping liquidity for protocols integrated with USX and EUX).
- Facilitate cross-chain expansion (i.e., provide bridging liquidity powered by treasury).

### **Key POO Primitives**

**Protocol-Controlled-Staking-Assets**

This strategy will significantly enhance organic and sustainable borrowing for underlying staking assets (i.e., ETH, ATOM, etc), introducing higher saving interest to underlying staking assets suppliers, and capturing staking yield as protocol revenue for DF holders.

Technically, it allows dForce to borrow underlying staking tokens (i.e., ETH) from dForce Lending, and convert to liquid staking tokens (i.e., wstETH backed by Lido, etc) for immediate access to staking yield.

The interest rate curve ensures that the borrowing interest rate is always capped below the staking yield. The protocol will recycle the staking rewards minus the borrowing interest as revenue.

As long as the borrow interest rate is lower than the staking yield, the protocol will be able to generate protocol revenue (staking rewards minus the borrowing interest expense) and potentially, with leverages.

[](https://docs.usx.finance/~gitbook/image?url=https%3A%2F%2F3195309216-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F8Qz6Wp9AI1XXGRr73nr8%252Fuploads%252FJg0HmbCxDFBDtB4VIPtp%252F002.png%3Falt%3Dmedia%26token%3Dae0f309e-6bbe-41d1-b4b4-fc57b5a46e29&width=768&dpr=4&quality=100&sign=f2d6f14&sv=1)

**Protocol-Controlled-Treasury**

This strategy allows dForce to lend, borrow, trade assets held by Treasury to seek yield and maximize protocol-controlled value.

For example, dForce can use treasury assets as collateral to mint USX or borrow from lending, and back liquidity provision denominated with USX as a base pair (USX/USDC, USX/DAI, etc) on DEXes. dForce can buy and sell to rebalance the pool algorithmically and collect arbitrage profits.

In the above example, dForce is able to acquire and control most of the liquidity for dForce assets in the open market, maintaining a sustainable growth without the need to over-incentivize liquidity supply with high APY. In addition, the protocol itself, not the user, owns the LP tokens, thereby generating transaction fees from the liquidity pool.

### **Risk Mitigation**

In order to adequately manage risk and reduce downside exposures associated with POO operations, we performed multiple stress-testing and have initially capped the POO limit at 50m USX through [DIP022](https://snapshot.org/#/dforcenet.eth/proposal/0x3dbd850691e293e92019015f9a0d1e8c6be32c49173ed378a5989410829d16c5).

POO limit can be further adjusted to meet the protocol growth expectation through governance and jointly decided by DF holders.

# **sUSX**

## What is sUSX?

Savings USX (sUSX) is the tokenized version of yield-bearing USX, redistributing revenue from dForce protocols back to USX holders.

Savings USX (sUSX) implements a LayerZero OFT (Omnichain Fungible Token) format for USX deposited into the sUSX vault, converting the USR-deposited position into a token users can hold and use.

sUSX will offer omni yields to holders across multiple networks, allowing USX holders to share in protocol revenues with the dForce DAO in proportion to the amount of USX deposited into the sUSX vault. This encourages long-term liquidity contributions to both USX and dForce.

## Omni yield everywhere

sUSX offers unified and consistent yield across multiple networks. This means that users can earn saving yield on their USX deposited into the sUSX contract, regardless of which blockchain they are using.

sUSX is initially launched on Ethereum, Arbitrum, Optimism, Base, and BSC, with the same native-yield (16% APY as approved through [DIP066](https://snapshot.org/#/dforcenet.eth/proposal/0x84fd286e387c576204e60b19ea38f59794865e5817c7ddc4d4f4cfd82f909233)).

To facilitate omni-yield harvesting, users can deposit USX into the sUSX contract on Chain A, bridge the sUSX received to Chain B, and redeem it for USX directly on Chain B.

By synchronizing yield rates across multiple chains, sUSX simplifies the user experience. Users do not need to worry about moving their USX between chains to maximize returns.

### Where does the yield come from?

xUSX will redistribute revenues collected by the Treasury from all dForce protocols and its eco-projects to sUSX holders, including but not limited to:

- Unitus Finance: interest spread allocation
- Vault: minting fees
- LSR: redemption fees, and saving interest generated by underlying collateral assets supplied to lending protocols
- POO: DeFi rewards
- Other RWA and other market operation strategies

Earnings automatically accrue and compound continuously while you hold sUSX.

### Can I use sUSX elsewhere?

Yes. Unitus has enabled sUSX as a collateral-only asset, allowing users to utilize sUSX as collateral to borrow other assets. This will help further enhance capital efficiency, enabling users to earn additional DeFi yields on top of the sUSX saving rate

## How to get sUSX?

sUSX is initially launched on Ethereum, Arbitrum, Optimism, Base, and BSC, with the same native-yield (15% APY as approved through [DIP066](https://snapshot.org/#/dforcenet.eth/proposal/0x84fd286e387c576204e60b19ea38f59794865e5817c7ddc4d4f4cfd82f909233)).Please go to [USX dapp](https://app.usx.finance/#/sUSX) and make sure you have switched to one of the supported L1/L2 networks.

![Untitled](USX%20-%202024%206/Untitled.png)

Enter the amount of USX you'd like to stake, and click on 'Approve' to continue.

![Untitled](USX%20-%202024%206/Untitled%201.png)

You will receive sUSX as a receipt for your staked USX after you approve the transaction.

## Omni-yield everywhere

sUSX offers unified and consistent yield across multiple networks. This means that users can earn saving yield on their USX deposited into the sUSX contract, regardless of which blockchain they are using.

sUSX is initially launched on Ethereum, Arbitrum, Optimism, Base, and BSC, with the same native-yield (15% APY as approved through [DIP066](https://snapshot.org/#/dforcenet.eth/proposal/0x84fd286e387c576204e60b19ea38f59794865e5817c7ddc4d4f4cfd82f909233)).

To facilitate omni-yield harvesting, users can deposit USX into the sUSX contract on Chain A, [bridge](https://bridge.dforce.network/) the sUSX received to Chain B, and redeem it for USX directly on Chain B.

By synchronizing yield rates across multiple chains, sUSX simplifies the user experience. Users do not need to worry about moving their USX between chains to maximize returns.

## How to get sUSX?

Please go to [USX dapp](https://app.usx.finance/#/sUSX) and make sure you have switched to one of the supported L1/L2 networks.

Click on the switch button in the center, and enter the amount of sUSX you'd like to redeem for USX. Confirm in your wallet to complete the process.

![Untitled](USX%20-%202024%206/Untitled%202.png)

sUSX will be burned and redeemed USX and yields will be sent to your wallet directly. 

# Bridge

[dForce Bridge](https://bridge.dforce.network/) supports cross-chain swaps for dForce-backed assets (USX, sUSX, DF, UTS) at minimized cost.

We don’t charge any fees for the cross-chain swap, but users still need to pay gas fees on both the original and the destination network to facilitate the swap.

![Untitled](USX%20-%202024%206/Untitled%203.png)

# Developer

## Contracts

- Ethereum: [0x0a5e677a6a24b2f1a2bf4f3bffc443231d2fdec8](https://etherscan.io/token/0x0a5e677a6a24b2f1a2bf4f3bffc443231d2fdec8)
- Arbitrum: [0x641441c631e2f909700d2f41fd87f0aa6a6b4edb](https://arbiscan.io/token/0x641441c631e2f909700d2f41fd87f0aa6a6b4edb)
- Optimism: [0xbfD291DA8A403DAAF7e5E9DC1ec0aCEaCd4848B9](https://optimistic.etherscan.io/address/0xbfD291DA8A403DAAF7e5E9DC1ec0aCEaCd4848B9)
- Base: [0xc142171B138DB17a1B7Cb999C44526094a4dae05](https://basescan.org/token/0xc142171B138DB17a1B7Cb999C44526094a4dae05)
- BSC: [0xb5102cee1528ce2c760893034a4603663495fd72](https://www.bscscan.com/token/0xb5102cee1528ce2c760893034a4603663495fd72)
- Polygon: [0xCf66EB3D546F0415b368d98A95EAF56DeD7aA752](https://polygonscan.com/address/0xCf66EB3D546F0415b368d98A95EAF56DeD7aA752)
- Avalanche: [0x853ea32391AaA14c112C645FD20BA389aB25C5e0](https://snowtrace.io/token/0x853ea32391aaa14c112c645fd20ba389ab25c5e0)
- KAVA: [0xDb0E1e86B01c4ad25241b1843E407Efc4D615248](https://explorer.kava.io/address/0xDb0E1e86B01c4ad25241b1843E407Efc4D615248/transactions)