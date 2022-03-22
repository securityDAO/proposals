# secdao-2
**TL;DR** switch to manual bounties as % of weekly yield only 🤠 compensation until the structured recurring compensation w/ peer feedback through `cw-ubi` is shipped / another proposal to resume is passed + improve multisig security by establishing a new multisig using a well-reviewed contract
## Why
![image](https://user-images.githubusercontent.com/1236584/159340485-127d084f-f8ae-4240-ab3b-820d1c186956.png)

We ☯️ want to compensate contributors at the level commensurate with the realized value of receiving their time, attention, and care. 🌱

At the same time, to optimally allocate DAO's treasury, rather than drawing payments to contributors weekly unconditionally (unsustainable at the current burn rate), we would instead prefer a shift to:
- the model of using yield on staking, DeFi instruments and other regenerative sources of `$TOKEN` for any recurring payments with areas of responsibility and expectations defined explicitly and subject to consensus and periodic performance review
- any direct payment to be reserved for **completed** contributions to the DAO that are well-specified in advance as *bounties* and **not to exceed the yield on principal for that week** (est. at `300 $JUNO` / week for the entire DAO)
- any unclaimed yield to be re-allocated to the total token invested in the yield-generating instrument subject to **secdao multisig** governance by Saturday midnight or delegated to **SecurityDAO Junø validator**



# What
- signal a pause in manually submitted weekly UBI payments **pending another proposal defining their precise structure** - the pause is to ensure that in the process of bootstrapping SecurityDAO, enough liquid funds are available for any operational needs that may arise between `2022-03-22` and the next infusion of funds
- properly incentivize atomic / one-time contributions on the critical path to fulfilling DAOs mission with a system of bounties defined in `secdao-3`
- transition **WAGMI** to **secdao multisig** that uses a more secure CosmWasm contract and includes the option to use a hardware `Ledger` wallet with `junod`
- start realizing yield on the token that is in the treasury now and not designated for bounty payouts
- replace 

A compensation scheme that involves a recurring payment in an agreed-upon amount of token to individual contributor wallets is warranted when the scope of a given task or broad ownership area (e.g. ensuring infrastructure uptime) requires _rare_ knowledge on an ongoing basis, and if various factors (e.g. original research, decision autonomy) make it impossible to specify a well-defined bounty ahead of time.

In the course of SecurityDAOs operation from the time of the [IWP-5](https://github.com/InterWasm/DAO/blob/main/IWPs/iwp-5.md) grant until now, a simple structure for weekly payments of `256 $JUNO - full-time, 128 $JUNO - part-time` (+ corresponding [advance](https://github.com/secdao/proposals/blob/secdao-02-feedback/multisig/secdao-1.md) to @devcubed) was instituted and served us well in attracting and retaining contributors. Over time, this structure has shown its limitations as an incentive mechanism that delivers timely outcomes and now needs revision.

This stops with the passing of the current proposal and henceforth the previous arrangement will be referred to as `ubi-legacy`. At the same time while `cw-ubi` and `cw-bounty` standard contracts that will codify the new incentives for individual contributors (in themselves, subject to funding by several ongoing [grant proposals](https://github.com/secdao/grants/pull/1)), 


`secdao-2` (this proposal) describes the steps to prepare the DAO to this new mode of operation, signals the stop of `ubi-legacy`

`secdao-3` provides the initial list of bounties and their rewards as % of the weekly yield, as well as procedures for defining, completing, and rewarding the initial set of bounties

`secdao-4` specifies initial yield-generating instruments whose yield will fund the bounties

## On-chain actions
* last UBI payout from [WAGMI](https://daodao.zone/multisig/juno1zn6wefwh00cuara90ctn7aqyfnhh34djyqnpd8w83z0x9ta88m6q5lq4tp) under the legacy scheme until `cw-ubi`
  - covers all contributions between `2022-03-06 - 2022-03-19`
  - token payments in the following amounts:
    - `256 $JUNO` to @netlenka
    - `256 $JUNO` to @rakataprime
    - `256 $JUNO` to @bmorphism
    - `256 $JUNO` to @CrashLoopBackOff
    - (already advanced) `256 $JUNO` to @devcubed
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
