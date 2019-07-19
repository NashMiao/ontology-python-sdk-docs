## Async RPC

```python
from ontology.sdk import Ontology

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
from ontology.sdk import Ontology

sdk = OntologySdk()
sdk.aio_rpc.connect_to_test_net()
version = await sdk.aio_rpc.get_version()
```

Gets the current node version asynchronously.

### get networkid

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
sdk.rpc.connect_to_test_net()
version = await sdk.aio_rpc.get_network_id()
```

<aside class="success">
Nodes with same networkid can join to a network.
<ul>
<li>0: Main Ontology Network.</li>
<li>1: Polaris Test Network.</li>
<li>0: Solo Test Network.</li>
</ul>
</aside>

Gets the current network ID asynchronously.

### get merkle proof

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
sdk.aio_rpc.connect_to_test_net()
tx_hash = '12943957b10643f04d89938925306fa342cec9d32925f5bd8e9ea7ce912d16d3'
merkle_proof = await sdk.aio_rpc.get_merkle_proof(tx_hash)
```

Gets merkle proof of specific transaction asynchronously.

![](merkle-tree.png)

<aside class="success">
The merkle root is one component of the block header, so in effect the merkle root is a cryptographic commitment to the transactions included in the block.
</aside>
