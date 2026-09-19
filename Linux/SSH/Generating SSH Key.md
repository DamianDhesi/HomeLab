Can use SSH key gen to generate keys using different algorithms, rounds of key derivations, etc. 
```
ssh-keygen
```
- by default uses ed25519 which is elliptic curve
	- elliptic curve is nice since it generates shorter but still secure keys compared to RSA
- stored in .ssh/

managing ssh public keys on all hosts can be a pain in large team settings but for smaller teams (or 1 person) it works well compared to using an alternative like ssh certificates 