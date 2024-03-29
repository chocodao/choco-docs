# FAQ

## Why do we need Choco Finance in the first place?

Dollar-pegged stablecoins have become an essential part of crypto due to their lack of volatility compared to tokens such as Bitcoin and Ethereum. Cryptocurrency users are comfortable with transacting using stablecoins believing that they will hold the same amount of purchasing power today vs. tomorrow. It is important to consider both sides, though: the dollar is controlled by the US government and the Federal Reserve, so a depreciation of the dollar also means a depreciation of its relative stablecoins.

Choco Finance aims to solve this aforementioned problem by creating an unpegged reserve currency — BARS — backed by an array of assets. By focusing on supply growth rather than price appreciation, Choco Finance foresees BARS function as a currency that is able to hold its purchasing power regardless of market volatility.

## Is BARS a stablecoin?

No, BARS is not a stablecoin. Rather, BARS aspires to become a reserve currency backed by other decentralized assets. Similar to the idea of the gold standard, BARS provides a free-floating value its users can always fall back on.

## What is the difference between backed and pegged tokens?

Think pegged = 1, while backed >= 1.

Each BARS is backed by a minimum of 1 USDC, not pegged to it. Because the treasury backs every BARS with at least 1 USDC, the protocol will buy back and burn BARS when it trades below its USDC backing value, causing its price to return back to its backing. BARS can always trade above 1 USDC because there is no upper limit imposed by the protocol.

## How does Choco work?

At a high level, Choco consists of its protocol-managed treasury and liquidity, melting mechanism, and molding rewards, in a manner designed to control supply expansion.

Melting pot sales generate profit for the treasury, which uses the profit to mold BARS and distributes them to molders. Liquidity-based melting pots allow the protocol to accumulate its own liquidity.&#x20;

## Why is Protocol Controlled Value important?

Since the protocol controls the funds in its treasury, BARS can only be minted or burned by the protocol. This guarantees that the protocol can always back 1 BARS with 1 USDC minimum; the protocol will indefinitely buy BARS as long as the price is below 1 USDC with the treasury assets.&#x20;

**It's hard to trust the feds, but you can always trust the code.**

As the protocol accumulates more Protocol Controlled Value (PCV), more runway is guaranteed for the molders. This means the molders can be confident that the current molding APY will be sustained for the long term.

## Why is Protocol Owned Liquidity important?

Choco owns a majority of its liquidity thanks to its melting mechanism. This has several benefits:

*   Choco does not have to pay out high farming rewards to incentivize liquidity

    providers a.k.a renting liquidity.
*   Choco guarantees that there is always significant liquidity to facilitate large

    trades in both size and volume.
* Choco earns almost all of the LP fees, another source of income for the treasury.
* Choco uses LP to back BARS. The LP tokens are marked down to their risk-free                      value for this purpose.&#x20;

## What will happen if there is a bank run?

Fractional reserve banking works because depositors don’t withdraw their funds all at once. A depositor’s faith in the banking system rests on regulations and agencies like Federal Deposit Insurance Corporation (FDIC).

BARS does not have FDIC insurance, but it has an incentive structure that protects molders. Let’s take a look at how it performs during a hypothetical bank run. In this scenario, we assume the majority of molders would panic and unmold their tokens from Choco - the molding percentage which stands at 92% now quickly collapses to 3.3%, leaving only 5,500 BARS molded.

Next, we assume the Risk-Free Value (RFV) inflows to the treasury completely dry up.&#x20;

Finally, we assume that those last standing molders bought in at a price of $500 per BARS. The initial investment of these molders would be:

$$
\$500/BARS * 5,500\ BARS = \$2.75\ million
$$

Say the total BARS supply is 2,000,000 and the RFV is $6,000,000. Remember that 1 BARS is backed by 1 USDC. Assuming 1 USDC = $1, subtracting these two numbers, we can find 4,000,000 BARS will eventually get issued to the remaining molders. In roughly a year, these molders who are holding 5,500 BARS will have:

$$
5,500 + 4,000,000 = 4,005,500\ BARS
$$

$2.75 million investment made by these molders will turn into about $4 million based on cash flow alone if they stay molded (recall that 1 BARS is backed by a minimum of 1 USDC). In this bank-run scenario, the molders who stay molded not only get their money back but also make some profit.&#x20;

## Why is the market price of BARS allowed to be volatile?

At launch, the Choco protocol will be tuned for expansion of BARS supply, which when paired with the molding, melting, and yield mechanics of Choco Finance, results in a reasonable amount of volatility.

BARS could trade above its backing because the market is willing to pay a premium to capture a percentage of the current market capitalization. However, the price of BARS could also drop by a large degree if the market sentiment turns. There may be significant price volatility during our growth phase so please **do your own research (DYOR)** on whether this project suits your goals.

## What is a rebase?

Rebase is a mechanism by which your molded BARS balance gains interest automatically. All newly minted BARS go to the molders. They will, instead, see a WRPR balance as opposed to BARS, allowing the protocol to utilize the rebase mechanism to increase the WRPR balance so that 1 WRPR is always redeemable for 1 BARS.

## What is reward yield?

Reward yield is the percentage by which your WRPR balance increases on the next epoch. It is also known as _rebase rate_. You can find this number on the Choco molding page.

## What is APY?

APY stands for annual percentage yield. It is a measure of the real rate of return on your principal by taking into account the effect of compounding interest. In the case of Choco Finance, your molded BARS represent your principal, and the compound interest is added periodically on every epoch (2200 Theta RPC blocks, or around 8 hours) thanks to the rebase mechanism.

With APY your balance will grow not linearly, but exponentially over time! Assuming a daily compound interest of 2%, if you start with a balance of 1 BARS on day 1, after a year, your balance will grow to about 1376.

![](https://3531032088-files.gitbook.io/\~/files/v0/b/gitbook-legacy-files/o/assets%2F-MV4hwONledQK5nEDaUc%2Fsync%2F585854ca21f006875c918ba2aed711730f71284a.png?generation=1622037634126699\&alt=media)

## How is the APY calculated?

The APY is calculated from the reward yield (a.k.a rebase rate) using the following equation:

$$
APY = ( 1 + rewardYield )^{1095} - 1
$$

The equation is raised to the power of 1095 because a rebase happens 3 times daily. There are 365 days in a year, this would give a rebase frequency of 365 \* 3 = 1095.

Reward yield is determined by the following equation:

$$
rewardYield = BARS_{distributed} / BARS_{totalMolded}
$$

The number of BARS distributed to the molding contract is calculated from BARS total supply using the following equation:

$$
BARS_{distributed} = BARS_{totalSupply} \times rewardRate
$$

Note that the reward rate is subject to change by the protocol.&#x20;

## What will be BARS' intrinsic value in the future?

There is no clear answer to this question, but the intrinsic value can be determined by treasury performance. For example, if the treasury could guarantee to back every BARS with 100 USDC, the intrinsic value will be 100 USDC.

## How will the protocol manage to maintain the high molding APY?

Let’s say the protocol targets an APY range of 1,000% to 10,000%, this would translate to a _minimum_ reward yield of about 0.2192%, or a daily growth of about 0.6577%. Please refer to the equation above to learn [how APY is calculated from the reward yield](faq.md#how-is-the-apy-calculated).

If there are 100,000 BARS molded right now, the protocol would need to mint an additional 657.7 BARS to achieve this daily growth. This is achievable if the protocol can bring in at least $657.70 of daily revenue from melting pot sales. Even if the protocol doesn't bring in that much revenue, it can still sustain 1,000% APY for a considerable amount of time (see the Choco manage tab) due to the excess reserve in the treasury.

## Do I have to unmold and mold BARS on every epoch to get my rebase rewards?

No. Once you have WRPR in your wallet, its balance will auto-compound on every epoch. The increase in balance represents your rebase rewards.

## How do I track my rebase rewards?

You can track your rebase rewards by measuring the increase in your WRPR balance.

1\. Record down the Current Index value on the molding page when you first mold your BARS. Let's call this $$index_{i}$$.

2\. After molding for some time, if you want to determine how much your balance has increased, check the Current Index value again. Let's call this $$index_{f}$$.

3\. By dividing $$index_{f}$$ by $$index_{i}$$, you would get the rate at which your WRPR balance has increased.

$$
WRPR_{ratio} = index_{f} / index_{i}
$$
