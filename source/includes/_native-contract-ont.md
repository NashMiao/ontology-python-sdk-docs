## ONT

```python
from os import path

from ontology.sdk import Ontology

sdk = Ontology()
ont = sdk.native_vm.ont()
```

This module contains functions to manage Ontology digital asset Ontology Token which based on Native Contract.

<aside class="success">
Ontology uses a dual token (ONT and ONG) model. ONT is the coin and can be used for staking in consensus.
</aside>

### name

```python
from ontology.sdk import Ontology

sdk = Ontology()
token_name = sdk.native_vm.ont().name()
```

Returns the name of the token synchronously.

### symbol

```python
from ontology.sdk import Ontology

sdk = Ontology()
token_symbol = sdk.native_vm.ont().symbol()
```

Returns the symbol of the token synchronously.

### decimals

```python
from ontology.sdk import Ontology

sdk = Ontology()
decimals = sdk.native_vm.ont().decimals()
```

Returns the number of decimals the token uses synchronously.

<aside class="success">
The decimals of ONT is 0, which means to divide the token amount by 1 to get its user representation.
</aside>

### balance of

```python
from ontology.sdk import Ontology

sdk = Ontology()
balance = sdk.native_vm.ont().balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address synchronously.

### transfer

```python
from ontology.sdk import Ontology

sdk = Ontology()
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ont().transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to_address synchronously.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>

### approve

```python
from ontology.sdk import Ontology

sdk = Ontology()
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ont().approve(owner, spender, 10, owner, 500, 20000)
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
from ontology.sdk import Ontology

sdk = Ontology()
owner = 'Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn'
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ont().allowance(owner, spender)
```

Returns the amount which spender is still allowed to withdraw from owner.

### transfer from

```python
from ontology.sdk import Ontology

sdk = Ontology()
spender = sdk.wallet_manager.create_account('password')
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = sdk.native_vm.ont().transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to_address.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>
