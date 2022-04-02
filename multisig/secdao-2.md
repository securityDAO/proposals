# ring-juno-validator multisig 🔑🔑🔑 ⬙ Junø mainnet validator 🔎⛓
![ring-juno-validator](https://user-images.githubusercontent.com/1236584/161363989-5d2cd3ae-f8cf-4374-956c-5d5ff0d452fc.jpeg)
## Members - suggested names for the commands below to work + PubKeys
- rakataprime `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A702+NkD5xO80qGR3jXzimxAT3RNC/bBDAuvHOO4tmLE"}'`
- bmorphism `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A5GqllzyaexmhEQWQN3YJlyvhEFFU7XoharP9F7+HGzi"}'`
- devcubed `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"AgJi4syK8t4yJQHt0KUneD4XWN9WfFWrDbveilQPXaxA"}'`
### Your own key vs those of other members
This guide assumes that as one of the members, you will be in possession of means to recover the private key.

Example: if I am in possession of the private key that corresponds to `AgJi4syK8t4yJQHt0KUneD4XWN9WfFWrDbveilQPXaxA`
`junod keys add devcubed --recover` and the Bech32 magic phrase.

Naming it `devcubed` as suggested is optional and will make the steps below not require modification.
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
#### Generate JSON by adding `--generate-only > secdao-junod-validator.json` to the CLI command
`secdao-juno-validator.json`:

```
{"body":{"messages":[{"@type":"/cosmos.staking.v1beta1.MsgCreateValidator","description":{"moniker":"SecurityDAO","identity":"","website":"https://secdao.xyz","security_contact":"","details":"Intergalactic Pegging Intelligence Agency"},"commission":{"rate":"0.133700000000000000","max_rate":"0.150000000000000000","max_change_rate":"0.010000000000000000"},"min_self_delegation":"1","delegator_address":"juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r","validator_address":"junovaloper1n33nhm7fes7umlw58lld77pkgh7qlp8lhupe76","pubkey":{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A4XqzRYBOY+F9oguxP2tG5J3DeenDPqt+SKHIi8scafS"},"value":{"denom":"ujuno","amount":"500"}}],"memo":"","timeout_height":"0","extension_options":[],"non_critical_extension_options":[]},"auth_info":{"signer_infos":[],"fee":{"amount":[{"denom":"ujuno","amount":"5000"}],"gas_limit":"200000","payer":"","granter":""}},"signatures":[]}
```
#### Sign using individual keys
##### Prerequisities
- private local key of the signing member needs to be recovered and added as suggested name for commands to work
- keys of other multisig members need to be added as well using `junod keys add --pubkey=<entire single quote string from Members>`
- multisig needs to be derived, i.e. `junod keys add ring-juno-validator --multisig=bmorphism,rakataprime,devcubed --multisig-threshold=2` is run

To check, you could verify that the output of the `junod keys list | grep name` has the same entities (may be in different order):

```
- name: bmorphism
- name: devcubed
- name: rakataprime
- name: ring-juno-validator
```

If the output contains all these, you are ready to execute your specific signing command below.

##### Individual steps
###### @bmorphism
```
junod tx sign \
    secdao-junod-validator.json \
    --multisig=juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r \
    --from=bmorphism \
    --output-document=sjv-b.json \
    --node https://rpc-juno.nodes.guru:443 \
    --chain-id=juno-1
```
###### @devcubed
```
junod tx sign \
    secdao-junod-validator.json \
    --multisig=juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r \
    --from=devcubed \
    --node https://rpc-juno.nodes.guru:443 \
    --output-document=sjv-d.json \
    --chain-id=juno-1
```
###### @rakataprime
```
junod tx sign \
    secdao-junod-validator.json \
    --multisig=juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r \
    --from=rakataprime \
    --node https://rpc-juno.nodes.guru:443 \
    --output-document=sjv-r.json \
    --chain-id=juno-1
```

#### Files are combined in one staging location and signed together

```
junod tx multisign \
    secdao-junod-validator.json \
    ring-juno-validator \
    sjv-b.json sjv-d.json rjv-r.json \
    --node https://rpc-juno.nodes.guru:443 \
    --chain-id=juno-1 > sjv-quorum-signed.json
```
#### Broadcast the fully signed message on-chain
```
junod tx broadcast sjv-quorum-signed.json \
    --node https://rpc-juno.nodes.guru:443 \
    --chain-id=juno-1 \
    --broadcast-mode=block
```
