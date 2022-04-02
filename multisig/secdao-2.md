# Instantiate ring-juno-validator
## Members (PubKeys)
- @rakataprime: `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A702+NkD5xO80qGR3jXzimxAT3RNC/bBDAuvHOO4tmLE"}'`
- @bmorphism: `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A5GqllzyaexmhEQWQN3YJlyvhEFFU7XoharP9F7+HGzi"}'`
- @devcubed: `'{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"AgJi4syK8t4yJQHt0KUneD4XWN9WfFWrDbveilQPXaxA"}'`
## Cosmos SDK multisig
```
junod keys add multi --multisig=bmorphism,rakataprime,devcubed --multisig-threshold=2

- name: multi
  type: multi
  address: juno1n33nhm7fes7umlw58lld77pkgh7qlp8lgphk9r
  pubkey: '{"@type":"/cosmos.crypto.multisig.LegacyAminoPubKey","threshold":2,"public_keys":[{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"AgJi4syK8t4yJQHt0KUneD4XWN9WfFWrDbveilQPXaxA"},{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A5GqllzyaexmhEQWQN3YJlyvhEFFU7XoharP9F7+HGzi"},{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"A702+NkD5xO80qGR3jXzimxAT3RNC/bBDAuvHOO4tmLE"}]}'
  mnemonic: ""
  ```
## Rename the old validator
Name: `InsecurityDAO`
Logo: <>
Commission: `13.37%`
Website: `https://secdao.xyz`
Minimum self-delegation: `1 $JUNO`
## Establish new validator using the multisig
Name: `SecurityDAO`
Logo: <>
Details: Intergalactic Pegging Intelligence Agency
Commission: `13.37%`
Website: `https://secdao.xyz`
Minimum self-delegation: `1 $JUNO`

