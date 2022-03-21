# secdao-2
**TL;DR** Switch to manual bounties-only 🤠 compensation until the structured recurring compensation w/ peer feedback through `cw-ubi` is shipped / another proposal to resume is passed
## Why
![image](https://user-images.githubusercontent.com/1236584/159340485-127d084f-f8ae-4240-ab3b-820d1c186956.png)

We ☯️ want to compensate contributors at the level commensurate with the realized value of receiving their time, attention, and care. 🌱

To do so, we need to depart from the default expectations in the lifecycle of startups under corporate models of governance 🏢: **at the outset**, labor exploitation and below market wages with ISOs carrying promises of eventual riches, then, **typically following a large funding round** - a spending and hiring frenzy governed through a narrow decision authority (and biases!).

DAOs carry a promise of more efficiently allocating capital, and come with a hope of more sustainable ways of scaling organizations and attracting contributors.

**Desiderata**

- the record of individual's contributions is made explicit (e.g. through `git`)
- the overall merit and concrete impact of contributions on DAO's overall realized value can be sufficiently isolated
- some part of DAOs value can be made liquid and the treasury has enough for slippage / longer reconciliation cycles (e.g. through payments for services in an already-liquid token, a token of the DAO itself, grants etc)
- pathways to onboard and contribute to the DAO are prominent and expectations are set clearly

Assuming all of these hold, it is not only _possible_ to strive to offer highly competitive effective hourly rates to the contributors right away (through a combination of **UBI + bounties**), it is _imperative_ upon us to find a way to do so in the context of broader emancipatory project of freeing the human spirit from the confines of wage slavery. ⚑✊

# What
This proposal seeks to:

- signal a pause in manually submitted weekly UBI payments **pending another proposal defining their precise structure** - the pause is to ensure that in the process of bootstrapping SecurityDAO, enough liquid funds are available for any operational needs that may arise between now (2022-03-21) and the next infusion of funds
- benefit from a unique moment in `$STARS - $ATOM` liquidity mining yield opportunities for the treasury funds
- properly incentivize atomic / one-time contributions on the critical path to fulfilling DAOs mission with a system of bounties
- create impetus for transitioning the treasury to a multisig (so as to adjudicate bounty completion with on-chain governance)

A compensation scheme that involves a recurring payment in an agreed-upon amount of token to individual contributor wallets is warranted when the scope of a given task or broad ownership area (e.g. ensuring infrastructure uptime) requires _rare_ knowledge on an ongoing basis, and if various factors (e.g. original research, decision autonomy) make it impossible to specify a well-defined bounty ahead of time.

In the course of SecurityDAOs operation from the time of the[IWP-5](https://github.com/InterWasm/DAO/blob/main/IWPs/iwp-5.md) grant until now, a simple structure for weekly payments of `256 $JUNO - full-time, 128 $JUNO - part-time` was instituted and served us well in attracting and retaining contributors.

Over time, this structure has shown its limitations as an incentive mechanism that delivers timely outcomes and now needs revision.

`secdao-2` aims to make this pause in UBI explicit, propose concrete ways in which the treasury can be allocated in the meantime that can be verifiably executed on-chain.

## Actions to be carried out on-chain
* deploy `16,000 $UST` equivalent of treasury at the time of execution to [`$STARS / $ATOM` liquidity pool on Osmosis #611](https://info.osmosis.zone/pool/611) with 14 days unbonding period (maximum yield)
* establish a **secdao multisig** for bounties (3/5 passing threshold) with the following on the multisig:
  - @netlenka
  - @devcubed
  - @CrashLoopBackoff
  - @rakataprime
  - @bmorphism
* transfer remaining funds from `IWP-5.md` to the multisig for allocation to bounties with subsequent governance decisions

## Actions to be carried out off-chain
* define initial set of high level goals for the DAO and `$TOKEN` allocations for bounties to help achieve them - they can then be broken down into specific bounties in subsequent proposals
* consensus on a fair bounty lifecycle, to also act as `cw-bounty` functional requirements and seed its spec in the grant proposal
* prepare shell scripts to quickly pay out the bounty when fulfilled (i.e. `Msg` templates with the right payout amounts and customizable adddress) by executing a command that uses `junod --ledger <>` type interaction with the multisig
