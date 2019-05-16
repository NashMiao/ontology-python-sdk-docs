# HD Wallet

<aside class="warning">
This package has <strong>NOT</strong> been audited and might potentially be unsafe. Take precautions to clear memory properly, store the private keys safely, and test transaction receiving and sending functionality properly before using in production!
</aside>

## get master keys

```python
from ontology.crypto.hd_private_key import HDPrivateKey

mnemonic = 'obscure worry home pass museum toss else accuse limb hover denial alpha'
master_keys = HDPrivateKey.master_key_from_mnemonic(mnemonic, 'password')
```

### get root keys

```python
from ontology.crypto.hd_private_key import HDPrivateKey

mnemonic = 'obscure worry home pass museum toss else accuse limb hover denial alpha'
master_keys = HDPrivateKey.master_key_from_mnemonic(mnemonic, 'password')
root_keys = HDPrivateKey.from_path(self.master_keys[0])
```

### get private child key

```python
from ontology.crypto.hd_private_key import HDPrivateKey

mnemonic = 'obscure worry home pass museum toss else accuse limb hover denial alpha'
master_keys = HDPrivateKey.master_key_from_mnemonic(mnemonic, 'password')

root_keys = HDPrivateKey.from_path(master_keys[0])
for i in range(10):
  child_sks = HDPrivateKey.from_path(root_keys[-1], '{change}/{index}'.format(change=0, index=i))

```

### get public child key

```python
from ontology.crypto.hd_public_key import HDPublicKey

mnemonic = 'obscure worry home pass museum toss else accuse limb hover denial alpha'
master_keys = HDPrivateKey.master_key_from_mnemonic(mnemonic, 'password')
root_keys = HDPrivateKey.from_path(master_keys[0])

root_pk = root_keys[-1].public_key
for i in range(10):
  child_pks = HDPublicKey.from_path(root_pk, '{change}/{index}'.format(change=0, index=i))

```
