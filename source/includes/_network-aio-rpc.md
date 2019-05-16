## Async RPC

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
sdk.aio_rpc.connect_to_test_net()
sdk.aio_rpc.connect_to_main_net()
sdk.aio_rpc.connect_to_localhost()
```

You can interact with Ontology network by JSON-RPC in asynchronously.

- connect to polaris test net.
- connect to main net.
- connect to the node in localhost.
- connect to the user-defined node.

### get version

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
sdk.aio_rpc.connect_to_test_net()
version = await sdk.aio_rpc.get_version()
```

### get merkle proof

```python
from ontology.ont_sdk import OntologySdk

sdk = OntologySdk()
sdk.aio_rpc.connect_to_test_net()
tx_hash = '12943957b10643f04d89938925306fa342cec9d32925f5bd8e9ea7ce912d16d3'
merkle_proof = await sdk.aio_rpc.get_merkle_proof(tx_hash)
```

![](merkle-tree.png)