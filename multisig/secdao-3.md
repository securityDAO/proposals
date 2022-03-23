
# secdao-3
**TL;DR** Regenerative Bounty System Description

## Why
<!-- ![image](https://user-images.githubusercontent.com/1236584/159340485-127d084f-f8ae-4240-ab3b-820d1c186956.png) -->

# What

`secdao-3` (this proposal) provides the initial list of bounties and their rewards as % of the weekly yield, as well as procedures for defining, completing, and rewarding the initial set of bounties

* Estabilish a bounty pool system on a monthly cadence ( All bounties are determined / outlined at the begining of a month based on yield farming and validator rewards only. The bounty payout will never be allowed to exceed the weekly rewards. If a multiweek bounty were to exceed the max cap for the week, the total bounties for the week would added together and payed out each week on a linearly scaled basis to each of the recipients. This will reset at the end of the month or defined sprint end


Who can apply for bounties?
* Only preapproved members may apply for bounties.  members can be added to bounty eligibilty list either through permissionless test or through permissioned and sponsored application.  Permissioned applications require public open source cosmwasm contributions and a sponsor who already is bounty-eligible 

Who determines who gets bounties in case of multiple applicants?
* SecDao Core Dev-1 group will be responsbile for bounty designation and adminstration inlcuding determination of completion status

Bounty Schedule:
* Bounties will be scheduled on a calendar month basis with the last week before the next calendar month used for planning purposes. 

Bounty Sizing:
* Bounties are sized as a percent of total regenerative yields per week for the Dao and structured as a part of a larger one month sprint

Bounty Weekly Cap:
* Bounty payout will never be allowed to exceed the weekly rewards. If a multiweek bounty were to exceed the max cap for the week, the total bounties for the week would added together and payed out each week on a linearly scaled basis to each of the recipients. This will reset at the end of the month or defined sprint end

Bounty Pools:
* 90% of bounty pool is pre-accolated to vision-centric main pool tasks related to grants, audits, or smart contracts
* Examples of tasks that qualify for main pool include audit template, audit sales, audit formatting, audit drafting, audit intake and presales, grant drafting, audit vulnerabilty finding, and smart contract development.
* Examples of tasks that are explicitly excluded from the main pool tasks are all non-rust software development efforts, devops tasks, cloud infrastructure management tasks, validator-related maintaince / monitoring, travel to conferences, internal time spent on bounty system interactions, git issue curation tasks, and social media posts\

Adversarial Bounty Theft
* bounties may be stolen from by other non-initiating members without consent of the bounty initiating member if the bounty completion is late for any task
* for milestone bounties bounty theft protection is waived for all subseqent or dependent tasks in sprint following the first late task stolen
* bounties that are stolen will only return 75% of the original to the non-initiating member and with the initiating member receiving 25% pending a multisig vote with 50% of members voting in favor.

Exemptions:
* Deviations from this compensation policy may only be completed by a 2/3 majority vote where the beneficiary (person or persons benefitting) are forced to abstain in their vote
* Dao may vote to make grants out of the treasury as a year end bonus with only a simple majority vote. Daoist must be contributing for at least 6 months to be eligbile to be included on the year end multisig

`secdao-4` specifies initial yield-generating instruments whose yield will fund the bounties

## On-chain actions
* last UBI payout from [WAGMI](https://daodao.zone/multisig/juno1zn6wefwh00cuara90ctn7aqyfnhh34djyqnpd8w83z0x9ta88m6q5lq4tp) under the legacy scheme until `cw-ubi`
  - covers all contributions between `2022-03-06 - 2022-03-19`
  - token payments in the following amounts:
    - `256 $JUNO` to @netlenka
    - `256 $JUNO` to @rakataprime
    - `256 $JUNO` to @bmorphism
    - `256 $JUNO` to @CrashLoopBackOff
    - (already [advanced](https://github.com/secdao/proposals/blob/secdao-2-3-refi/multisig/secdao-1.md)) `256 $JUNO` to @devcubed
* those willing to become secdao multisig members will need to [establish](https://docs.junonetwork.io/cli/modules/keys) `junod` wallets using CLI - either add new keys, import existing ones using the seedphrase `junod keys add --recover`, or start one with `junod add keys --ledger` if Ledger - subsequently, these will be referred to as [HumanAddr{@GitHubUsername}](https://docs.rs/cosmwasm-std/0.9.2/cosmwasm_std/struct.HumanAddr.html)
- wallet addresses provided to `#treasury` within 24 hours of this proposal passing will be included in subsequent steps
* instantiate our own **secdao multisig** contract using [`junod` interactions](https://docs.junonetwork.io/smart-contracts-and-junod-development/tutorial-erc-20/initialise)
  - new instance of [cw3-fixed-multisig](https://github.com/CosmWasm/cw-plus/tree/main/contracts/cw3-fixed-multisig) for `junod` / [Message](https://docs.rs/cosmwasm-std/0.16.6/cosmwasm_std/enum.WasmMsg.html)-based governance with the following configuration (`3/5 votes` passing threshold, `24 hours` timeout):
      ```
      {
      ...
      "voters": 
      [
        {"addr": "HumanAddr{@netlenka}", "weight": 1},
        {"addr": "HumanAddr{@rakataprime}", "weight": 1},
        {"addr": "HumanAddr{@bmorphism}", "weight": 1},
        {"addr": "HumanAddr{@CrashLoopBackOff}", "weight": 1},
        {"addr": "HumanAddr{@devcubed}, "weight": 1}],
      "threshold": 3,
      "max_voting_period": 86400
      ...
      }
      ```
  * to be used for governance around bounty payouts and treasury allocation, prioritizing on-chain Message-driven proposals
* after backing up the seed phrase, delete and re-import wallets locally, transfer `4.20 $JUNO` from **WAGMI** and make sure multisig interactions with `junod` are still possible
* following a successful test, transfer the remaining funds from `IWP-5.md` to the multisig for allocation to bounties with subsequent governance decisions
* accept any additional grants from individuals into **secdao multisig** treasury as `$JUNO` sent to multisig address - each `256 $JUNO` in an individual grant will be rewarded with a **secdao-awarded** `SG-721` NFT that has **no utility or governance impact** (but _could_ be used in airdrop decisions when transitioning to DAOs and subDAOs following completion of [dao-contracts](https://github.com/DA0-DA0/dao-contracts/tree/zeke/contracts-v1/contracts) audit and transition to `v1` contracts for governance)

## Off-chain actions
* to coincide with this proposal being in `main`, also arrive at the soft consensus about (`#gov` signaling) and merge [secdao-3](https://github.com/secdao/proposals/blob/secdao-02-feedback/multisig/secdao-3.md) containing
  * initial set of high level goals for the DAO and `$TOKEN` allocations for bounties to help achieve them - they can then be broken down into specific bounties in subsequent proposals
  * precise bounty lifecycle definition to be manually executed as **secdao multisig** votes until `cw-bounty` is shipped - capturing result of soft consesus in `#gov`
* instructions on how to use `junod` for the purposes of this proposal by @bmorphism to be added to GitHub + sent to `#gov`
* (everyone) collaborate on shell scripts to quickly pay out the bounty when fulfilled - ultimately to help individual members with `junod` CLI [Message interactions](https://github.com/CosmWasm/cw-plus/blob/main/contracts/cw3-fixed-multisig/src/msg.rs#L24)
  * submit a proposal: `Propose`
  * vote on a proposal: `Vote`
  * execute a proposal that passes: `Execute`
  * close proposals that time out: `Close`

# Goals
