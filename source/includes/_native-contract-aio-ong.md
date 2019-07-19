## Async ONG

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
ong = sdk.native_vm.aio_ong()
```

This module contains functions to manage Ontology digital asset Ontology Gas which based on Native Contract.

<aside class="success">
Ontology uses a dual token (ONT and ONG) model. ONG is the utility token used for on-chain services.
</aside>

### name

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
token_name = await sdk.native_vm.aio_ong().name()
```

Returns the name of the token asynchronously.

### symbol

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
token_symbol = await sdk.native_vm.aio_ong().symbol()
```

Returns the symbol of the token asynchronously.

### decimals

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
decimals = await sdk.native_vm.aio_ong().decimals()
```

Returns the number of decimals the token uses asynchronously.

<aside class="success">
The decimals of ONG is 9, which means to divide the token amount by 1000000000 to get its user representation.
</aside>

### balance of

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
balance = await sdk.native_vm.aio_ong().balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address asynchronously.

### unbound

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
sdk.rpc.connect_to_test_net()
address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
unbound_ong = await sdk.native_vm.aio_ong().unbound(address)
```

Unbound ONG is an amount of ONG which has not been added to your claimable ONG balance yet (since it only updates each time you make an ONT transaction in your wallet address). When an ONT transaction is made in your address, the claimable ONG balance will update (adding your unbound ONG amount to your claimable ONG amount).

<aside class="success">
Claimable ONG is the amount of ONG you can claim for a 0.01 ONG fee. This balance will update each time an ONT transaction is made in your wallet address.
</aside>

### transfer

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ong().transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to_address asynchronously.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>

### approve

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ong().approve(owner, spender, 10, owner, 500, 20000)
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

sdk = OntologySdk()
owner = 'Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn'
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ong().allowance(owner, spender)
```

Returns the amount which spender is still allowed to withdraw from owner.

### transfer from

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
spender = sdk.wallet_manager.create_account('password')
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = await sdk.native_vm.aio_ong().transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to_address.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>
