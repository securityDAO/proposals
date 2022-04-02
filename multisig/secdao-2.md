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
### junod CLI command
```
junod tx staking create-validator --amount 500ujuno --commission-max-change-rate "0.01" --commission-max-rate "0.15" --commission-rate "0.1337" --min-self-delegation "1" --website "https://secdao.xyz" --details "Intergalactic Pegging Intelligence Agency" --pubkey=$(junod tendermint show-validator) --moniker 'SecurityDAO' --chain-id juno-1 --gas-prices 0.025ujuno --from juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r
```

### junod JSON to be signed by the multisig
#### Generate JSON by adding `--generate-only > ring-junod-validator.json` to the CLI command
`ring-juno-validator.json`:

```
{"body":{"messages":[{"@type":"/cosmos.staking.v1beta1.MsgCreateValidator","description":{"moniker":"SecurityDAO","identity":"","website":"https://secdao.xyz","security_contact":"","details":"Intergalactic Pegging Intelligence Agency"},"commission":{"rate":"0.133700000000000000","max_rate":"0.150000000000000000","max_change_rate":"0.010000000000000000"},"min_self_delegation":"1","delegator_address":"juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r","validator_address":"junovaloper1n33nhm7fes7umlw58lld77pkgh7qlp8lhupe76","pubkey":{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A4XqzRYBOY+F9oguxP2tG5J3DeenDPqt+SKHIi8scafS"},"value":{"denom":"ujuno","amount":"500"}}],"memo":"","timeout_height":"0","extension_options":[],"non_critical_extension_options":[]},"auth_info":{"signer_infos":[],"fee":{"amount":[{"denom":"ujuno","amount":"5000"}],"gas_limit":"200000","payer":"","granter":""}},"signatures":[]}
```
#### Sign using individual keys
##### @bmorphism
```
junod tx sign \
    ring-junod-validator.json \
    --multisig=juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r \
    --from=bmorphism \
    --output-document=rjv-b.json \
    --chain-id=juno-1
```
##### @devcubed
```
junod tx sign \
    ring-junod-validator.json \
    --multisig=juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r \
    --from=devcubed \
    --output-document=rjv-d.json \
    --chain-id=juno-1
```
##### @rakataprime
```
junod tx sign \
    ring-junod-validator.json \
    --multisig=juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r \
    --from=rakataprime \
    --output-document=rjv-r.json \
    --chain-id=juno-1
```

#### Files are combined in one staging location and signed together

```
junod tx multisign \
    ring-junod-validator.json \
    ring-juno-validator \
    rjv-b.json rjv-d.json rjv-r.json \
    --chain-id=juno-1 > rjv-quorum-signed.json

#### Broadcast the fully signed message on-chain
```
junod tx broadcast rjv-quorum-signed.json \
    --chain-id=juno-1 \
    --broadcast-mode=block
```
