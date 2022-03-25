![gmi](https://user-images.githubusercontent.com/1236584/159620261-462f7475-5ac8-4061-957f-3ebcf8ad9624.png)

# secdao-2 - a more perfect consensus 🕹
`cw3-flex-multisig` instances

## CTF
### ring-wasm
Examples:

https://github.com/CosmWasm/cw-plus#compiling 🌌 your daily Pluriverse alpha leaks post 🙆🏽 -- for those who code -- if you have gone through these steps _in the past_ for whatever reasons (don't cheat by doing so now or claiming that you did, you will not make it - i.e. eventual ngmi 😝) -- but if you have ever run the command cited or a related relevant command, and especially in the context cw20, there is a meritdrop you can ape into if you additionally encrypt the secret string in the Junø contract at <> -- and sign it using your private key with junod

In the already-complied `.wasm` file there is a string that identifies it as belonging to a particular organization - what is that organization? (Hint: you need to use a wasm disassembler and extract strings / convert to the right encoding to be able to display)
## multisigs (future DAOs and subDAOs)
### DAO ring-0 {Ledger required}
- owns de::ns
- gets all treasury funds now there
- carries out treasury allocation

@daoistone:1, @daoisttwo:1, ..., @daoistn:1, @ring-legal: n + 1 {effectively veto power for instance!}
@fellowtravelerone: 0, ... and everyone has to be a non-voting member: 0,
 
threshold: 100% only
### subDAO seed: ring-infra - 100 points
@paul: 1, @tom: 1, @olena: 0, @logan: 1 and everyone else who is not 1
#### Release an automated deployment (ie: docker, ansible) of a juno full node on the juno-1 mainnet (ie: docker, ansible) that is fully synced with the chain. Then submit the message that states your node is fully synced, and any code used to achive that state.
### subDAO seed ring-wasm - 100 points
@barton: 1, @tom: 0, @olena: 0
- develops individual grants and actually carries out bounties
### ... ring-defi - 100 points
- maximizes yield
#### Generate a 30 day change history of JUNO using code (not copy pasting from a website). Then submit the change history and that code used to generate it.
### ring-uiux - 100 points
- a dApp that has Keplr integration and allows one to sign strings entered into a text field with their private key
- create a interaction flow for a hardware wallet that doesn't sucks
### ring-redteam - 100 points
- run a pentest against a horcrux-using validator
- fork a testnet that has badly configured validators
### ring-legal - 100 points
@barton: 1, @logan: 1, @olena: 1, @tom: 1, @paul: 1
- drives legal structures for various jurisdictions
- handles defense / offense expenses
### ring-fellow-travelers - 100 points
(educational, never more than $1k equiv, everyone starts with `weight: 1` - every new member starts with ability to experiment with low stakes)
- the first rung of interaction with the DAO - newcomers
- Execute contract interactions - submit proposals, vote on proposals, submit proposals to other rings that are gated more strongly ^^
- {evil mode} submit a proposal that changes governance in a way that favors them or breaks it / denial of service (in which case they advance to weight: 1 on red-team, if infra attack - ring-infra weight: 1, if contract level ring-wasm weight: 1)
## On-chain actions
### Transfer ownership over [secdao](https://dens.sh/ids/secdao) name to ring-0 (`<to be instantiated>`) from `IWP-5` funds wallet (`juno1j37...`)
### Transfer treasury and any assets in Osmosis or otherwise part of `IWP-5` funds to ring-0
### Define compensation primitives and execute on them (e.g. the substance of )
### Fund treasuries of each individual multisig if necessary for ongoing costs or projects

## **BELOW is PREVIOUS DRAFT, INTEGRATE AFTER ADDRESSING THE CORE POINTS**
Following extensive code review ahead of the [Prop 17 unity proposal](https://commonwealth.im/juno/discussion/4102-prop-17-unity-win-win-win) being put to a vote and should it pass, a pressisng need for an audited multisig contract to remove risks to `$JUNØ` [CCN token saga](https://twitter.com/JoeAbbey/status/1506327517296308240) through inclusive [governance as code](https://github.com/DA0-DA0/dao-contracts/blob/zeke/contracts-v1/contracts/cw3-multisig/src/contract.rs#L116), [we at SecurityDAO](https://secdao.xyz) are ready to declare `cw3-fixed-multisig` secure and move **all of our liquid token** / governance to it!

On-chain contract address of audited `cw3-fixed-multisig`: <>

Following the execution of this proposal, any hack that results in loss of treasury funds or persistent denial of the ability of voting **secdao multisig** members to engage in timely governance, **by that token alone** would constitute the ultimate **self-funding bounty**, as well as a guaranteed way to impress us! 😉 **#SkinInTheGame**

**TL;DR**

⬙ switch on-chain governance for **SecurityDAO** to an instance of the [well-reviewed cw3-fixed-multisig contract](https://github.com/DA0-DA0/dao-contracts/tree/zeke/contracts-v1/contracts/cw3-multisig) governed _uniformly_ (`"weight": 1`) by the current full-time contributors and using the `.wasm` contract codebase compiled from [`6b98d8a`]() (crucially, after the fix resolving the `Addr` vulnerability (ref `SEC-03`) - that was independently discovered by [@ezekiiel](https://github.com/ezekiiel) and **SecurityDAO** as a part of an authorized audit of an unrelated CosmWasm contract

⬖ switch [secdao de(NS)](https://dens.sh/tokens/secdao) to point at the new multisig contract instance's treasury and move all of the remaining treausry token from [`IWP-5`](https://github.com/InterWasm/DAO/blob/main/IWPs/iwp-5.md) grant, as well as the [experimental public DAO DAO instance's `10 $JUNO`](https://daodao.zone/dao/juno1p9w4u6nlrwc6gdg3cyrvzlh3tuacsyqfl4vadkh02pjeh0zsrnksd93z0c) to the new contract's treasury (sans any nominal fees incurred in de(NS) name update, conversion to `$JUNO`, and governance)

⬘ begin accepting individual contributions in `$JUNO` to the treasury and generating **secdao cw721 art** to be given in recognition 🎨

⬗ switch comp away from UBI and towards bounties rewarded with % of weekly yield on DAO's treasury - exact process clarified in [secdao-3](https://www.youtube.com/watch?v=o-YBDTqX_ZU) 🤠 (reintroduction of recurring comp pending completion of the `cw-ubi` implementation of Coordinape-like protocol in CosmWasm w/ peer review)

⬙ allocate multisig treasury to yield-generating instruments subject to multisig governance and a spread outlined in proposal [secdao-4]()

⬖ allow for a limited time welcoming of sponsored non-voting multisig members (`"weight": 0`) to be added to the voting set as advisors and fellow travelers using a simplified web-of-trust model (pseudonymous wallets with optional KyC, but at least one existing multisig member needs to vouch through signatures); the new non-voting members will be able to join all non-privileged collaboration spaces in GitHub, Element, ProtonCalendar, as well as participate in soft consensus / vision-setting and even contribute to code in the same way other DAOists do today and, most importantly, submit on-chain proposals to the multisig (though [not votes](https://github.com/DA0-DA0/dao-contracts/blob/zeke/contracts-v1/contracts/cw3-multisig/src/contract.rs#L236), and naturally be eligible for engagement and contribution-dependent airdrop of governance token for SecurityDAO or its area-specific SubDAOs when we transition to `DAO DAO v1` contracts


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
* last UBI payout from [WAGMI](https://daodao.zone/multisig/juno1zn6wefwh00cuara90ctn7aqyfnhh34djyqnpd8w83z0x9ta88m6q5lq4tp) under the legacy scheme until `cw-ubi` is shipped
  - covers all contributions between `2022-03-06 - 2022-03-19`
  - token payments in the following amounts:
    - `256 $JUNO` to @netlenka
    - `256 $JUNO` to @rakataprime
    - `256 $JUNO` to @bmorphism
    - `256 $JUNO` to @CrashLoopBackOff
    - (already [advanced](https://github.com/secdao/proposals/blob/secdao-2-3-refi/multisig/secdao-1.md)) `256 $JUNO` to @devcubed
* those willing to become secdao multisig members will need to [establish](https://docs.junonetwork.io/cli/modules/keys) `junod` wallets using CLI - either add new keys, import existing ones using the seedphrase `junod keys add --recover`, or start one with `junod add keys --ledger` if Ledger
  - after backing up your new wallet's keys / mnemonic seed phrase, delete and try reimporting wallets locally with `junod` to convince yourself that you can
  - if you want to be on the new multisig, you will need to make a commit to this file while it is still under review, replacing the corresponding [`HumanAddr{@GitHubUsername}`](https://docs.rs/cosmwasm-std/0.9.2/cosmwasm_std/struct.HumanAddr.html) below with the resulting wallet address to be used with `junod tx wasm instantiate` message
  - you will be expected to use this wallet to participate in on-chain **governance around bounties, selecting yield instruments for treasury, and any other valid CosmWasm contract interactions through [`Messages`](https://docs.rs/cosmwasm-std/0.16.6/cosmwasm_std/enum.WasmMsg.html) to be put forth with a multisig proposal**. Also, while doing so, you need to be comfortable **using `junod` client CLI and scripts that aid in its use** (Keplr integration / custom UI are possible in the future, but not presently prioritized)
  - if you are comfortable with this responsibility, please make the commit containing your actual address at any point up until this branch remains unmerged into `main`, preceding the [**WAGMI** vote](https://daodao.zone/multisig/juno1zn6wefwh00cuara90ctn7aqyfnhh34djyqnpd8w83z0x9ta88m6q5lq4tp) on DAODAO
  - anyone who does not commit their address to the proposal in time will still be included using their last known address, but with `weight: 0`, i.e. they will retain access to current **secdao** Element rooms, this repository, as well as use `junod` to raise proposals for multisig votes - they will not, however, be able to vote as such
  - the exact `voters` block resulting from this process to be used to initialize the new multisig with [`junod` interactions](https://docs.junonetwork.io/smart-contracts-and-junod-development/tutorial-erc-20/initialise) to make the new instance of [cw3-fixed-multisig](https://github.com/CosmWasm/cw-plus/tree/main/contracts/cw3-fixed-multisig) for `junod` / [Message](https://docs.rs/cosmwasm-std/0.16.6/cosmwasm_std/enum.WasmMsg.html)-based governance with the following voting configuration (`3/5 votes` passing threshold, `24 hours` timeout):
      ```
      {
      ...
      "voters": 
      [
        {"addr": "HumanAddr{@netlenka}", "weight": 2},
        {"addr": "juno12f9k9a922qpzcwmgt50utd5cfa5ksnl0q33yxh", "weight": 3},
        {"addr": "HumanAddr{@bmorphism}", "weight": 3},
        {"addr": "juno1mz3z4q89zlycut3yv07mej0cvlgx3kdcxg3u27", "weight": 1},
        {"addr": "HumanAddr{@devcubed}, "weight": 3},
        {"addr": "juno1rvazh6ck86jqtckc3n3cprp0dkuv2zkcwwn3tm", "weight": 0},
        {"addr": "juno175q6smvgnuec5e62rs4chnu5cs8d98q2xgf4rx", "weight": 0}],
      "threshold": 7,
      "max_voting_period": 86400
      ...
      }
      ```
* run several tests using `4.20 $JUNO` extra token currently in **WAGMI** through the now-established **secdao multisig**
  - transfer `1 $JUNO` to the new multisig's treasury
  - divide the remainder among all multisig wallets for gas fees in voting
  - attempt to run through `Propose`, `Vote`, `Execute`, `Close` interactions and verify the multisig works as expected
* only following several successful tests, transfer the remaining funds from the `IWP-5.md` grant and any additional funds to the multisig treasury

### Additional funds and growth 📈
#### Future grants
Barring another approved proposal stating otherwise (e.g. one to migrate the treasury and governance to instances of `DAO DAO v1` contracts), approved funds for any grant applications will need to be delivered to the **secdao multisig wallet address** as `$JUNO` or `cw-20` `$TOKEN` if in Junø.

If the `$TOKEN` is not in `$JUNO` or liquidity is not available, the funds can be converted and sent to an approved `CosmWasm` contract that is controlled by the **secdao multisig** [over IBC](https://github.com/CosmWasm/cosmwasm/tree/main/contracts/ibc-reflect)
#### Sponsoring a non-voting secdao member
##### Context
We want to allow for growth in **trusted secdao members**, to operate as a DAO [in public](https://www.audible.com/pd/Working-in-Public-Audiobook/B08KWQ1G7X) with transparency and skin in the game as much as possible without jeopardizing privileged information for our mission or individual safety of contributors, and, critical to our growth, to be able to enlist and reward advisors who could direct us to the relevant future contributors, audit targets, and other opportunities, as well as nudge us towards better decisions in general.

At the same time, we want the inclusion into governance to be a thoughtful process, that among other considerations propels us to:

- have strict meritocratic gating mechanisms that are based on merit and _relevant_ on-chain and other activities
  (some existing ideas include CosmWasm CTF questions / koans, **Cicada 3301** type challenges, public activity on GitHub / Twitter / aligned chat spaces)
- take time to establish value alignment on the core principles of [ethical hacking](https://www.eccouncil.org/ethical-hacking/) and **responsible disclosure vulnerability disclosure** that we seek to advance with incentives and education
- confirm that the candidate is in possession of the basic skills they would need to succeed in one of the DAO's roles when contributing in their chosen corner of consensus mechanism security (validator set, IBC and relayers, smart contracts and their runtime, endpoint opsec, front-ends, hot wallets, graph methods on txn data, and anything else)

##### Who is a nonvoting member
`cw3-fixed-multisig` contract proposed here allows for adding members to the voter set with `weight: 0` and the intent of this behavior is described in the `README.md` like so:

```
Note that 0 is an allowed weight. This doesn't give any voting rights, but it does allow that key to submit proposals that can later be approved by the voters. Any address not in the voter set cannot submit a proposal.
```

This presents an opportunity to begin building a group of fellow travelers interested in becoming more informed about and engaged in visioning for **SecurityDAO** (should they choose to accept the challenge!) without the risk of losing the atomic community to unsavory actors who game the initial set of on-chain governance mechanisms.

For a limited time only - until the proposal here is finalized and the new multisig contract instantiated (as the member list is then fixed) - it is possible to sponsor a new non-voting member from the **Pluriverse** or broader Junø / Cosmos community by vouching for them and donating on their behalf!

To sponsor a new non-voting secdao member, the following would need to take place:

- sponsor
- `32 $JUNO` (≈ `1000 $UST` as of writing) to [secdao wallet](https://dens.sh/dens::secdao)

#### Patrons of the dark arts ⚑
The **secdao multisig** treasury (once created) can accept any additional `$JUNO` from those inclined to support our cause - each `256 $JUNO` in an individual donation will additionally be awarded one **secdao `cw-721` Junø NFT** (max of 2). This NFT has **no utility** other than on-chain evidence of being a **fren of SecurityDAO**.

**Please note! 👮🏻‍♂️** (important legalese) while the presence of this NFT in a wallet _could_ be used in future airdrop decisions when transitioning the core governance to DAOs and area-specific governance to subDAOs, e.g. with [dao-contracts v1](https://github.com/DA0-DA0/dao-contracts/tree/zeke/contracts-v1/contracts) following the audit, it is important to very explicitly state here that in itself the NFT is not a security, does not confer governance powers, and one can opt out of receiving the said NFT entirely by including `ngmi` in the donation Memo

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
