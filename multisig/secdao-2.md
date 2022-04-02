# Instantiate ring-juno-validator
## Members (PubKeys)
- @rakataprime: `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A702+NkD5xO80qGR3jXzimxAT3RNC/bBDAuvHOO4tmLE"}'`
- @bmorphism: `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A5GqllzyaexmhEQWQN3YJlyvhEFFU7XoharP9F7+HGzi"}'`
- @devcubed: `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"AgJi4syK8t4yJQHt0KUneD4XWN9WfFWrDbveilQPXaxA"}'`
## Cosmos SDK multisig
```
junod keys add ring-juno-validator --multisig=bmorphism,rakataprime,devcubed --multisig-threshold=2

- name: ring-juno-validator
  type: multi
  address: juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r
  pubkey: '{"@type":"/cosmos.crypto.multisig.LegacyAminoPubKey","threshold":2,"public_keys":[{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"AgJi4syK8t4yJQHt0KUneD4XWN9WfFWrDbveilQPXaxA"},{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A5GqllzyaexmhEQWQN3YJlyvhEFFU7XoharP9F7+HGzi"},{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A702+NkD5xO80qGR3jXzimxAT3RNC/bBDAuvHOO4tmLE"}]}'
  mnemonic: ""
  ```
## Rename the old validator
| Field | Value |
| --- | ----------- |
| Name | Title |
| Logo | Text |
| Commission | |
| Website | |
| Minimum self-delegation | |

**Name:** `InsecurityDAO`

**Logo:** NA

**Commission:** `6.28%`

**Website:** `https://secdao.xyz`

**Minimum self-delegation:** `1 $JUNO`

## Establish new validator using the multisig
| Field | Value |
| --- | ----------- |
| Name | SecurityDAO |
| Logo | [https://keybase.io/secdao](https://s3.amazonaws.com/keybase_processed_uploads/641b0d5f17c12764f27f6aa49d31fe05_360_360.jpg) |
| Commission | 13.37% |
| Website | https://secdao.xyz |
| Description | Intergalactic Pegging Intelligence Agency |
| Minimum self-delegation | 1 `$JUNO` |
### junod CLI
```
junod tx staking create-validator \
  --amount 500ujuno \
  --commission-max-change-rate "0.01" \
  --commission-max-rate "0.10" \
  --commission-rate "0.1337" \
  --min-self-delegation "1" \
  --website "https://secdao.xyz" \ 
  --details "" \
  --pubkey=$(junod tendermint show-validator) \
  --moniker 'SecurityDAO' \
  --chain-id juno-1 \ 
  --gas-prices 0.025ujuno \
  --from juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r
```


