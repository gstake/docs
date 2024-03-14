# FAQs

## **How does Gstake for The Graph work?**

The Gstake protocol aggregates user deposits of GRT and stakes them on The Graph network. The wstGRT, minted by users, can be viewed as shares in Gstake, which entitle them to staking rewards generated from The Graph. When users redeem GRT using wstGRT, they initiate the redemption process on the network by burning wstGRT. This process enables them to withdraw both the principal and the accumulated staking rewards.

## **What is Gstake staking APR for The Graph?**

Gstake staking APR = The Graph Protocol APR \* (1 - Protocol fee)

## **What is reward fee? What is this used for?**

The protocol imposes a 10% fee on staking rewards. This fee is allocated for protocol upgrades, maintenance, and a risk assurance fund. As a result, users will receive 90% of the staking rewards distributed by the network.

## **What is stake tax?**

Gstake stakes GRT to The Graph protocol through a set of delegators. Each time a delegator stakes GRT to The Graph protocol, The Graph automatically destroys 0.5% of the total amount staked.

## **How does the withdrawal process work?**

The withdrawal process is simple and has two steps:

1. **Request withdrawal**: Lock your wstGRT by issuing a withdrawal request. GRT is sourced to fulfill the request, and then locked wstGRT is burned, which marks the withdrawal request as claimable. Under normal circumstances, this can take anywhere between 1-28 days.
2. **Claim**: Claim your GRT after the withdrawal request has been processed.

## **How long does it take to withdraw?**

Under normal circumstances, the wstGRT withdrawal period can take anywhere between 1-28 days. After that, you can claim your GRT using the Claim tab.

## **Do I still get rewards after I withdraw?**

No, you will not continue to receive rewards after you withdraw. Once you initiate a withdrawal, the wstGRT that you’ve unstaked will stop accruing staking rewards, meaning no additional rewards will be added to your submitted balance.

## **Is there a fee for withdrawal?**

There’s no withdrawal fee. However, similar to any Ethereum interaction, a network gas fee will apply. Please note that Gstake does not charge a fee when you request a withdrawal.

## **What is Gstake withdrawal NFT?**

Each withdrawal request is represented by an NFT: the NFT is automatically minted for you when you send a request. You will need to add it to your wallet to be able to monitor the request status. When the request is ready for the claim, the NFT will change its appearance.

## **How do I add the Gstake NFT to my wallet?**

Different wallets have specific functionalities for adding and working with NFTs. Most often, you need to find the specific NFT Address and Token ID. You can find these parameters on Etherscan. Visit Etherscan, add your wallet, and locate the NFT transaction. Once located, open the NFT transaction, and you will see the Address and Token ID.

## **What is Withdrawal limit?**

Gstake will delegate the user’s GRT to a group of delegators. However, it will only process the request for withdrawing coins through one delegator per day. Therefore, there will be a limit on the amount of coins that can be withdrawn each day. For more details, please refer to the mechanism of withdrawing coins.
