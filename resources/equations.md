# Equations

## Molding

$$
deposit = withdrawal
$$

Swaps between BARS and WRPR during molding and unmolding are always honored 1:1. The amount of BARS deposited into the molding contract will always result in the same amount of WRPR. And the amount of WRPR withdrawn from the molding contract will always result in the same amount of BARS.

$$
rebase = 1 - ( BARSDeposits / WRPROutstanding )
$$

The treasury deposits BARS into the distributor. The distributor then deposits BARS into the molding contract, creating an imbalance between BARS and WRPR. WRPR is rebased to correct this imbalance between BARS deposited and WRPR outstanding. The rebase brings WRPR outstanding back up to parity so that 1 WRPR equals 1 molded BARS.

## Melting

$$
meltingpot Price = 1 + Premium
$$

BARS has an intrinsic value of 1 USDC, which is roughly equivalent to $1. In order to make a profit from melting, Choco charges a premium for each melting pot.

$$
Premium = debt Ratio * MPCV
$$

The premium is derived from the debt ratio of the system and a scaling variable called MPCV, which allows us to control the rate at which melting pot prices increase.

The premium determines profit due to the protocol and in turn, molders. This is because new BARS is minted from the profit and subsequently distributed among all molders.

$$
debt Ratio = meltingpotsOutstanding/bars 
 Supply
$$

The debt ratio is the total of all BARS promised to melters divided by the total supply of BARS. This allows us to measure the debt of the system.

$$
melting potPayout_{reservemeltingpot} = marketValue_{asset}\ /\ meltingpotPrice
$$

Melting Pot payout determines the number of BARS sold to a melter. For reserve melting pots, the market value of the assets supplied by the melter is used to determine the melting pot payout. For example, if a user supplies 1000 USDC and the melting pot price is 250 USDC, the user will be entitled to 4 BARS.

$$
meltingpotPayout_{lpMeltingPot} = marketValue_{lpMeltingPot}\ /\ meltingpotPrice
$$

For liquidity melters, the market value of the LP tokens supplied by the melter is used to determine the melting pot payout. For example, if a user supplies 0.001 BARS-USDC LP token which is valued at 1000 USDC at the time of melting, and the melting pot price is 250 USDC, the user will be entitled 4 BARS.

## BARS Supply

$$
BARS_{supplyGrowth} = BARS_{molders} + BARS_{melters}
$$

BARS supply does not have a hard cap. Its supply increases when:

* BARS is minted and distributed to the molders.
* BARS is minted for the melter. This happens whenever someone purchases a melting pot.

$$
BARS_{molders} = BARS_{totalSupply} * rewardRate
$$

At the end of each epoch, the treasury mints BARS at a set reward rate. These BARS will be distributed to all the molders in the protocol.

$$
BARS_{molders} = meltingPotPayout
$$

## Backing per BARS

$$
BAR_{backing} = treasuryBalance_{stablecoin} + treasuryBalance_{otherAssets}
$$

Every BARS in circulation is backed by the Choco treasury. The assets in the treasury can be divided into two categories: stablecoin and non-stablecoin.

$$
treasuryBalance_{stablecoin} = RFV_{reserveMelting} + RFV_{lpMelting}
$$

The stablecoin balance in the treasury grows when melting pots are sold. RFV (Risk Free Value) is calculated differently for different melting pot types.

$$
RFV_{reserveMelting} = assetSupplied
$$

For reserve melting pots such as USDC, the RFV simply equals to the amount of the underlying asset supplied by the melter.

$$
RFV_{lpMelting} = 2sqrt(constantProduct) * (\%\ ownership\ of\ the\ pool)
$$

For LP melters such as BARS-USDC LP, the RFV is calculated differently because the protocol needs to mark down its value. Why? The LP token pair consists of BARS, and each BARS in circulation will be backed by these LP tokens - there is a cyclical dependency. To safely guarantee all circulating BARS are backed, the protocol marks down the value of these LP tokens, hence the name _risk-free_ value (RFV).
