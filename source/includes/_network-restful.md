## RESTful

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
sdk.restful.connect_to_test_net()
sdk.restful.connect_to_main_net()
sdk.restful.connect_to_localhost()
sdk.restful.set_address('http://localhost:20334')
```

You can interact with Ontology network by JSON-RPC in synchronously.

- connect to polaris test net.
- connect to main net.
- connect to the node in localhost.
- connect to the user-defined node.

### get version

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
sdk.restful.connect_to_test_net()
version = sdk.restful.get_version()
```

### get merkle proof

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
sdk.restful.connect_to_test_net()
tx_hash = '12943957b10643f04d89938925306fa342cec9d32925f5bd8e9ea7ce912d16d3'
merkle_proof = sdk.restful.get_merkle_proof(tx_hash)
```

![](merkle-tree.png)
