# Wallet Manager

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
wallet = sdk.wallet_manager
```

This module contains functions to manage Ontology digital accounts and digital identity (named ONT ID) which based on W3c DID protocol specification.

<aside class="warning">
This package has <strong>NOT</strong> been audited and might potentially be unsafe. Take precautions to clear memory properly, store the private keys safely, and test transaction receiving and sending functionality properly before using in production!
</aside>

## open wallet

```python
from os import path

from ontology.sdk import Ontology

sdk = OntologySdk()
wallet_path = path.join(path.curdir, 'wallet.json')
wallet = sdk.wallet_manager.open_wallet(wallet_path)
```

We can read wallet's KeyStore by using `open_wallet` interface, which will help us load KeyStore file in JSON format from disk into memory.

<aside class="notice">
Keystore is password encrypted private key that is in JSON file format, which is used to access your wallet. Because Keystore is already encrypted, it is relatively safe to keep the keystore file on your computer or notepad.
</aside>

## create account

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
wallet = sdk.wallet_manager.create_account('password')
```

<aside class="warning">
If the password is too easy, it can be easily exploited by brute force attack. We recommend using password of at least 8 characters, preferably more than 12 characters.
</aside>

## create identity

```python
from ontology.sdk import Ontology

sdk = OntologySdk()
wallet = sdk.wallet_manager.create_identity('password')
```

<aside class="warning">
If the password is too easy, it can be easily exploited by brute force attack. We recommend using password of at least 8 characters, preferably more than 12 characters.
</aside>

## get account by address

```python
from os import path

from ontology.sdk import Ontology

sdk = OntologySdk()
wallet_path = path.join(path.curdir, 'wallet.json')
wallet = sdk.wallet_manager(wallet_path)
acct = wallet.get_account_by_b58_address('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD', 'password')
```

## get identity by ont id

```python
from os import path

from ontology.sdk import Ontology

sdk = OntologySdk()
wallet_path = path.join(path.curdir, 'wallet.json')
wallet = sdk.wallet_manager(wallet_path)
ont_id = 'did:ont:ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
identity = wallet_manager.get_identity_by_ont_id(ont_id)
```

<aside class="success">
Ontology DID(named ONT ID) is a decentralized identification protocol which based on W3C DID specifications. ONT ID establishes a cryptographically-based digital identity for each entity.
</aside>
