## ONT ID

```python
from ontology.sdk import Ontology

sdk = Ontology()
ont_id = sdk.native_vm.ont_id()
```

### get public keys

```python
from ontology.sdk import Ontology

sdk = Ontology()
ont_id = 'did:ont:APywVQ2UKBtitqqJQ9JrpNeY8VFAnrZXiR'
pub_keys = sdk.native_vm.ont_id().get_public_keys(ont_id)
```

## Async ONT

```python
from ontology.sdk import Ontology

sdk = Ontology()
ont = sdk.native_vm.aio_ont()
```

## Async ONG

```python
from ontology.sdk import Ontology

sdk = Ontology()
ong = sdk.native_vm.aio_ong()
```

## Async ONT ID

```python
from os import path

from ontology.sdk import Ontology

sdk = Ontology()
sdk.native_vm.aio_ont_id()
```
