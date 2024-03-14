# Redemption Mechanism

Gstake users can redeem GRT by destroying wstGRT. The redemption process is as follows:

1. Users initiate a redemption request by destroying wstGRT through the core contract, and simultaneously mint a redemption NFT representing the redemption rights.
2. The Gstake operator processes redemption requests daily, matching redemption and staking requests. Small redemptions that are successfully matched can receive GRT on the same day. Large redemption requests that are not successfully matched initiate an undelegate request from TheGraph protocol through the delegator, and then need to wait for 28 days.
3. After 28 days, users can receive GRT.

Gstake operates a delegator daily to complete the redemption request. Due to the staking volume limit of each delegator, Gstake has a daily redemption quantity limit (**Withdrawal limit**).
