## ONT ID

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
ont_id = sdk.native_vm.ont_id()
```

### get public keys

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
ont_id = 'did:ont:APywVQ2UKBtitqqJQ9JrpNeY8VFAnrZXiR'
pub_keys = sdk.native_vm.ont_id().get_public_keys(ont_id)
```

## Async ONT

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
ont = sdk.native_vm.aio_ont()
```

## Async ONG

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
ong = sdk.native_vm.aio_ong()
```

## Async ONT ID

```python
from os import path

from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
sdk.native_vm.aio_ont_id()
```
