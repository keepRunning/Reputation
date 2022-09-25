## An protocol to manage reputation based on multi-party ratings

## Overview

A blockchain based ratings system which closely resembles a real life ratings model with a more balanced power model between a merchant/service-provider and the consumer.

Terms

1. Reputation Score - Indicates the entity’s current score on a 1-10 scale.
2. Rep token - A fungible token(ERC20) distributed as a reward for contributing to the system.

## Terms

- Merchant - A service provider or a seller.
- Customer - A person using a service or a buyer.
- Reputation Score(number) - A score representing the aggregate ratings of a Merchant or a Customer.
- REP Token(ERC20 token) - A platform token rewarded to both Merchants and Customers on participation.

## Pain points of the current system

1. Platform controlled and susceptible to capitalism.
2. Merchants can buy reputation score or remove comments/ratings hurting business without improving.
3. Once a large reputation score is achieved, average to good reputation is maintained for a long time even when all recent ratings are bad. 
4. A sudden drop in ratings, will not reflect at all until considerable time.
5. Most customers don’t give a rating. The only time they provide is to give a bad rating. This makes the system always biased for negative reviews. [Bias]
6. Most customers who give a positive review are coaxed or pressed to review by wait-staff or smooth-talking managers. [Bias]
7. Many customers might erroneously attribute service\delivery experience to product rating(misattributed ratings).
8. Some customers will always rate negatively.
9. Ratings are generic and rate a large number of categories together like waiting time, pricing, service, quality, etc.

## Proposal:

1. Create a reputation system with the following features
    1. Reward on providing ratings - In real life, recommendation is a social reward system. For the online system, we need to provide a REP token reward.
    2. Reward or Slash - Each rating needs to impact both parties. A positive rating will benefit both parties while a negative one will harm both. The difference between the current rating and the provided rating(or diff) will be passed on to both.
    3. Reconciliation:
        1. Rewarding correct behavior : If a negative trend has been prominently continuing, then when a correction happens, the users who have been provided negative ratings will be rewarded more. 
        2. Punishing greedy behavior: If a user always gives a positive review despite a trend of negatives, then the user is slashed.
        3. Punishing bad behavior: If a user always gives a negative reviews where others have indicated mostly positive reviews, then the user’s score and tokens will be reduced. The user’s negative review impact will also be removed pushing up the merchant’s score.
        4. The above decisions need to be carried out by trend/curve correlation and might be mathematically intensive. These can’t be part of a daily process. 
        5. They will need to be updated by the user(user’s app) and should be easily verifiable by others. This can be 
        6. The DAO controls the thresholds, customizable settings and entire modules. The REP holders will control the DAO as a community.
        

## Reputation Score

This is the final score that will indicate the reputation of the entity. This will be calculated and updated periodically based on ratings. This will change dynamically, rapidly and show a number of sub-reputations to indicate category based ratings. 

Many real-life scenarios will be taken into consideration such as

- Rapid decline - Continuous bad ratings will bring down the overall rating at an accelerated pace.
- Sliding time-frame - only ratings within a sliding window-timeframe will be used.
- Decay rule - All scores will decay slowly. Being active is the only way to keep it boosted. REP tokens will decay with time too.

## Rep Token

This is an ERC20 token that will be rewarded to both merchants and customers based on participation and accurate reviews.

### Usage

For Customers

1. Rep tokens are earned by providing reviews and by transfer from Merchants.
2. Rep tokens can be redeemed similar to reward points at Merchants.
3. Rep tokens can be converted to better your personal Reputation(up to a limit)

For Merchants

1. Rep tokens are earned by customer reviews.
2. Rep tokens can be received from Customers(in-lieu of offers/good-will).
3. Rep can be used to boost Ratings(up to a limit). This will help new business get visibility.
4. Rep cannot be transferred between merchants. They can only earned from customers.
5. Merchants with huge REP tokens can reward customers to improve loyalty.

## Benefits

1. Unified reputation platform for multiple use-cases.
2. Blockchain use-case with complete transparency.
3. Customers are rewarded with Rep tokens and Reputation.
4. Customer with good Reputation can get better service/rates.
5. Customers can redeem Rep tokens with new and upcoming Merchants.
6. Merchants can get steady and predictable reviews.
7. Merchants can get a more favorable Reputation Score.
8. New Merchants can boost their Reputation Score with Rep token.
9. Established Merchants can giveaway their Rep tokens to loyal customers.
10. Policies can be tweaked by a neutral DAO.

## The Process

1. The merchant or user can create the first transaction on-chain indicating an real-life transaction. The other party will have to accept it. We will have to use oracles to track off-chain transactions. 
2. Subsequently, once the real-life transaction is complete, the ratings will come into place. The customer(C) will create a review for the Merchant(M) and vice versa. Both will be tied to the firstly created transaction.

We might have a lot of connected users on this chain running a job to update all reputation will be in vain. Rather, we can allow users(or their d-apps) to trigger this after every nth transaction, day or a configurable number. This can be triggered by interested third parties too.

1. Reputation calculation -  This will calculate the reputation score of the entity. This will be part of the pluggable DAO controlled contract. By keeping calculations as part of a purely mathematical contract, the DAO can change the parameters and make meaningful upgrades.
2. Reconciliation - This will use trend/curve analysis or other statistical/ML tools to compare multiple reviews and find the non-matching reviews. We might need to write-in logic for a fair amount of tolerance for a Bad-day scenario. But with reasonable amount of data and good algorithms, we should be able to make this fairly accurate.
3. REP tokens - This will be rewarded immediately after leaving review. This will ensure immediate feedback and make this worth the effort. 

## Challenges to look forward to:

- Making this work would be a challenge. Apart from the insane calculations and real-life scenarios we will need to incorporate, we need to make reviewers feel valued. This should always accept a review from the reviewer while not hurting a genuine business from growing. Both parties need to have power in this.
- There are a lot of risks which we need to mitigate - User geo-locations and habits can be easily exposed by adding reviews. We need to enable a  system of anonymity to keep users safe while tracking and updating their scores.
