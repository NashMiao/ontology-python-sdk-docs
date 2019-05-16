## ONG

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
ong = sdk.native_vm.ong()
```

This module contains functions to manage Ontology digital asset Ontology Gas which based on Native Contract.

<aside class="success">
Ontology uses a dual token (ONT and ONG) model. ONG is the utility token used for on-chain services.
</aside>

### name

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
token_name = sdk.native_vm.ong().name()
```

This interface is used to get the name of the token synchronously.

### symbol

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
token_symbol = sdk.native_vm.ong().symbol()
```

This interface is used to get the symbol of the token synchronously.

### decimals

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
decimals = sdk.native_vm.ong().decimals()
```

This interface is used to the number of decimals the token uses synchronously.

<aside class="success">
The decimals of ONG is 9, which means to divide the token amount by 1000000000 to get its user representation.
</aside>

### unbound

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
sdk.rpc.connect_to_test_net()
address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
unbound_ong = sdk.native_vm.ong().unbound(address)
```

Unbound ONG is an amount of ONG which has not been added to your claimable ONG balance yet (since it only updates each time you make an ONT transaction in your wallet address). When an ONT transaction is made in your address, the claimable ONG balance will update (adding your unbound ONG amount to your claimable ONG amount).

<aside class="success">
Claimable ONG is the amount of ONG you can claim for a 0.01 ONG fee. This balance will update each time an ONT transaction is made in your wallet address.
</aside>
