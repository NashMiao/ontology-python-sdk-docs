## Async ONT

```python
from os import path

from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
ont = sdk.native_vm.aio_ont()
```

This module contains functions to manage Ontology digital asset Ontology Token which based on Native Contract.

<aside class="success">
Ontology uses a dual token (ONT and ONG) model. ONT is the coin and can be used for staking in consensus.
</aside>

### name

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
token_name = await sdk.native_vm.aio_ont().name()
```

Returns the name of the token asynchronously.

### symbol

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
token_symbol = await sdk.native_vm.aio_ont().symbol()
```

Returns the symbol of the token asynchronously.

### decimals

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
decimals = await sdk.native_vm.aio_ont().decimals()
```

Returns the number of decimals the token uses asynchronously.

<aside class="success">
The decimals of ONT is 0, which means to divide the token amount by 1 to get its user representation.
</aside>

### balance of

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
balance = await sdk.native_vm.aio_ont().balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address asynchronously.

### transfer

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ont().transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to_address asynchronously.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>

### approve

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ont().approve(owner, spender, 10, owner, 500, 20000)
```

Allows spender to withdraw from owner account multiple times, up to the value amount.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Approval event.
</aside>

<aside class="notice">
If this function is called again it overwrites the current allowance with amount value.
</aside>

### allowance

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
owner = 'Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn'
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ont().allowance(owner, spender)
```

Returns the amount which spender is still allowed to withdraw from owner.

### transfer from

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
spender = sdk.wallet_manager.create_account('password')
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = await sdk.native_vm.aio_ont().transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to_address.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>
