## ONT

```python
from os import path

from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
ont = sdk.native_vm.ont()
```

This module contains functions to manage Ontology digital asset Ontology Token which based on Native Contract.

<aside class="success">
Ontology uses a dual token (ONT and ONG) model. ONT is the coin and can be used for staking in consensus.
</aside>

### name

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
token_name = sdk.native_vm.ont().name()
```

This interface is used to get the name of the token synchronously.

### symbol

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
token_symbol = sdk.native_vm.ont().symbol()
```

This interface is used to get the symbol of the token synchronously.

### decimals

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
decimals = sdk.native_vm.ont().decimals()
```

This interface is used to the number of decimals the token uses synchronously.

<aside class="success">
The decimals of ONT is 0, which means to divide the token amount by 1 to get its user representation.
</aside>
