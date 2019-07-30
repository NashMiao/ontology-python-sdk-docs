## Async OEP-4

<aside class="warning">
This package has <strong>NOT</strong> been audited and might potentially be unsafe. Take precautions to clear memory properly, store the private keys safely, and test transaction receiving and sending functionality properly before using in production!
</aside>

### name

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
token_name = await oep4.name()
```

Returns the name of the token asynchronously.

### symbol

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
token_symbol = await oep4.symbol()
```

Returns the symbol of the token asynchronously.

### decimals

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
decimals = await oep4.decimals()
```

Returns the number of decimals the token uses asynchronously.

<aside class="success">
E.g. 9, means to divide the token amount by 1000000000 to get its user representation.
</aside>

### total supply

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
supply = await oep4.total_supply()
```

Returns the total token supply asynchronously.

### balance of

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
balance = await oep4.balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address asynchronously.

### init

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
founder = sdk.wallet_manager.create_account('password')
payer = sdk.wallet_manager.create_account('password')
tx_hash = await oep4.init(founder, payer, 500, 20000)
```

Contract owner uses this interface to activate oep-4 token asynchronously.

### transfer

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await oep4.transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to_address asynchronously.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>

### transfer multi

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
transfer_list = [[from_address1, to_address, 1], [from_address2, to_address, 1]]
signers = [from_acct1, from_acct2]
tx_hash = await oep4.transfer_multi(transfer_list, signers, payer, 500, 20000)
```

Transfers amount of token from from-account to to-account multiple times asynchronously.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>

### approve

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await oep4.approve(owner, spender, 10, owner, 500, 20000)
```

Allows spender to withdraw from owner account multiple times asynchronously, up to the value amount.

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
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await oep4.approve(owner, spender, 10, owner, 500, 20000)
```

Returns the amount which spender is still allowed to withdraw from owner asynchronously.

### transfer from

```python
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = await oep4.transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to_address asynchronously.

<aside class="success">
If this function is called successfully, it  <strong>MUST</strong> fire the Transfer event.
</aside>
