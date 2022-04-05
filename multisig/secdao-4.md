
# secdao-3

# Regenerative Bounty System 

# Why
`secdao-3` (this proposal) provides the initial list of bounties and their rewards as % of the weekly yield, as well as procedures for defining, completing, and rewarding the initial set of bounties>

# What

Estabilish a bounty pool system on a monthly cadence ( All bounties are determined / outlined at the begining of a month based on yield farming and validator rewards only. The bounty payout will never be allowed to exceed the weekly rewards. If a multiweek bounty were to exceed the max cap for the week, the total bounties for the week would added together and payed out each week on a linearly scaled basis to each of the recipients. This will reset at the end of the month or defined sprint end

Who can apply for bounties?
* Only preapproved members may apply for bounties.  members can be added to bounty eligibilty list either through permissionless test or through permissioned and sponsored application.  Permissioned applications require public open source cosmwasm contributions and a sponsor who already is bounty-eligible 

Who determines who gets bounties in case of multiple applicants?
* SecDao Core Dev-1 group will be responsbile for bounty designation and adminstration inlcuding determination of completion status

Bounty Schedule
* Bounties will be scheduled on a calendar month basis with the last week before the next calendar month used for planning purposes. 

Bounty Sizing
* Bounties are sized as a percent of total regenerative yields per week for the Dao and structured as a part of a larger one month sprint

Bounty Weekly Cap
* Bounty payout will never be allowed to exceed the weekly rewards. If a multiweek bounty were to exceed the max cap for the week, the total bounties for the week would added together and payed out each week on a linearly scaled basis to each of the recipients. This will reset at the end of the month or defined sprint end

Bounty Pools
* 90% of bounty pool is pre-accolated to vision-centric main pool tasks related to grants, audits, or smart contracts
* Examples of tasks that qualify for main pool include audit template, audit sales, audit formatting, audit drafting, audit intake and presales, grant drafting, audit vulnerabilty finding, and smart contract development.
* Examples of tasks that are explicitly excluded from the main pool tasks are all non-rust software development efforts, devops tasks, cloud infrastructure management tasks, validator-related maintaince / monitoring, travel to conferences, internal time spent on bounty system interactions, git issue curation tasks, and social media posts

Adversarial Bounty Theft
* bounties may be stolen from by other non-initiating members without consent of the bounty initiating member if the bounty completion is late for any task for milestone bounties bounty theft protection is waived for all subseqent or dependent tasks in sprint following the first late task stolen
* bounties that are stolen will only return 75% of the original to the non-initiating member and with the initiating member receiving 25% pending a multisig vote with 50% of members voting in favor.

Exemptions:
* Deviations from this compensation policy may only be completed by a 2/3 majority vote where the beneficiary (person or persons benefitting) are forced to abstain in their vote
* Dao may vote to make grants out of the treasury as a year end bonus with only a simple majority vote. Daoist must be contributing for at least 6 months to be eligbile to be included on the year end multisig

`secdao-4` specifies initial yield-generating instruments whose yield will fund the bounties

## On-chain actions

This will be implemented using `cw-bounty` starting for April 2022, as first bounty.  

# Off-chain actions

Further development of procedures and processes may occur offchain.

# Goals
