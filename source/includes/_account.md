# Account

## get address

```python
from ontology.utils import utils
from ontology.account.account import Account

private_key = utils.get_random_bytes(32).hex()
account = Account(private_key)
address = account.get_addres()

```

<aside class="notice">
Every account has a unique address, and there is a private key that corresponds one-to-one to this address. Private key acts like a password here.
</aside>

## export wif

```python
from ontology.utils import utils
from ontology.account.account import Account

private_key = utils.get_random_bytes(32).hex()
account = Account(private_key)
wif = account.export_wif()

```

<aside class="success">
WIF is Wallet Import Format, an error-correcting and shortened format for private key and make it easier to copy.
</aside>
