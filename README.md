# satyam-oct-16-wallet

```
aztec-wallet create-account -a my-wallet
```

Response

```
Address:         0x0ee6bb2a01f701a29ad7e56edc95aec05d311f10eeb7389b72cf644530571042
Public key:      0x288d47129378303b12bf97059baac15f857f116094ca1afe067e819887be3da1176992defdcea53511cbdd1f639bda9997a271fb0531075a1b52a0faae07091e0c6abf4194a7eb0b19ca4dbf590ef230f9e1ca5f5412604e1e5d5c78f19d525d28d1f26e2d1c4f5526741a7aff4532674ffdab0b1712a2cc58e730e84a24a3df2f7cbcbdfa964fbe0ff359fa99d6cdf90c734c6a43383d9620bade52a5ff35a0261c78fefb91400c2979305b31a58d371fe48613d6c1e2e54cf5aa6798da787c14ae011fcf592a772efa16cd397ab70620ea91e544216c916cbf32ce7d171cb42989ca7109e75ef8b69bacd1e8aa2ad22d0885998d58312eb3092e9f4624af2f
Secret key:     0x2158bd6197c6ea519759f92db12db12cf2784f89d1207fbc01d0610624935cd6
Partial address: 0x291df793999196866e8723769d01b73b7d21bdfbcd0b8b81083abad5232f0086
Salt:            0x0000000000000000000000000000000000000000000000000000000000000000
Init hash:       0x2804b8eed2acd4a4bfcba2254c192800456f3b08f9161e8df8ef9ba02bf3e578
Deployer:        0x0000000000000000000000000000000000000000000000000000000000000000
```


To fetch your wallet

```
aztec-wallet get-alias accounts:satyam-oct-16-wallet
```



Deploy Token Contract

```
aztec-wallet deploy TokenContractArtifact --from accounts:satyam-oct-16-wallet --args accounts:satyam-oct-16-wallet TestToken TST 18 -a testtoken
```


Token Contract Deploy Response
```
Contract deployed at 0x183ae40525e47806c8159589c2f5129abfa9af8b50b1f5276caf288f9766582b
Contract partial address 0x2318a165175de6357c61bb993cc69a5412c7d9c5d2da3c9f7939a71e1b8ba5dc
Contract init hash 0x1c5e1e1436153453cd8f7ecf01a1ae75413b06dcc072f33236b04dadefb261e0
Deployment tx hash: 2591ed9654bffa2cc7eb6d2dfcda4898351331e8054486a1b1f21474f3cf5007
Deployment salt: 0x239c11e81474c5e61f6cd5a2565118e6ab1669a446b2adc0e760ce4f6e0d43ea
Deployment fee: 213422582
Contract stored in database with aliases last & testtoken
```

Mint public tokens

```
aztec-wallet send mint_public --from accounts:satyam-oct-16-wallet --contract-address testtoken --args accounts:satyam-oct-16-wallet 100
```

```
aztec-wallet simulate balance_of_public --from satyam-oct-16-wallet --contract-address testtoken --args accounts:satyam-oct-16-wallet
```


Deploy Counter Contract

```
```
aztec-wallet deploy ./target/counter-Counter.json --from accounts:satyam-oct-16-wallet --args 2 accounts:satyam-oct-16-wallet accounts:satyam-oct-16-wallet -a countercontract
```
