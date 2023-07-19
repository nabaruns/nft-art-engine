# nft-art-engine

## Description

Demo script to generate NFTs from a folder of images.

## Installation

```bash
npm install
```

## Sample Input data directory structure

```bash
data
├── Background__z10
│   ├── Blue__w5.png
│   ├── Navy Blue__w10.png
│   └── Orange__w10.png
├── Body__z20
│   ├── Green__w10.png
│   ├── Grey__w10.png
│   └── Robot__w5.png
├── Clothing__z30
│   ├── Camo__w10.png
│   ├── Eye suite__w10.png
│   └── Santa__w10.png
├── Face__z40
│   ├── Old Face__w10.png
│   ├── Old Face__z-15.png
│   ├── Robot Face__w20.png
│   ├── Robot Face__z-15.png
│   ├── Zap Face__w10.png
│   └── Zap Face__z-15.png
└── Prop__z50
    ├── Backpack.png
    ├── Backpack__z-35__w10.png
    └── edge-cases
        ├── Backpack__z-35__tClothing__vSanta.png
        └── Backpack__z20__tClothing__vSanta.png
```

## Usage

```bash
node index.js
```

```bash
██╗  ██╗ █████╗ ███████╗██╗  ██╗██╗     ██╗██████╗ ███████╗    ██╗      █████╗ ██████╗
██║  ██║██╔══██╗██╔════╝██║  ██║██║     ██║██╔══██╗██╔════╝    ██║     ██╔══██╗██╔══██╗
███████║███████║███████╗███████║██║     ██║██████╔╝███████╗    ██║     ███████║██████╔╝
██╔══██║██╔══██║╚════██║██╔══██║██║     ██║██╔═══╝ ╚════██║    ██║     ██╔══██║██╔══██╗
██║  ██║██║  ██║███████║██║  ██║███████╗██║██║     ███████║    ███████╗██║  ██║██████╔╝
╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚══════╝╚═╝╚═╝     ╚══════╝    ╚══════╝╚═╝  ╚═╝╚═════╝

Art Engine 2.0.0-alpha4 👄
      
Loading data...
Generating...
Rendering...
Exporting...
Done
┌─────────┬──────────────────┬─────────────┬─────────────┬─────────────┬────────────┐
│ (index) │      Topic       │     Min     │     Max     │   Average   │   Total    │
├─────────┼──────────────────┼─────────────┼─────────────┼─────────────┼────────────┤
│    0    │ 'Loading inputs' │  '1.77 ms'  │  '1.77 ms'  │  '1.77 ms'  │ '1.77 ms'  │
│    1    │   'Generating'   │  '6.94 ms'  │  '6.94 ms'  │  '6.94 ms'  │ '6.94 ms'  │
│    2    │  'Image render'  │ '186.95 ms' │ '220.38 ms' │ '197.14 ms' │  '1.97 s'  │
│    3    │   'Rendering'    │  '1.97 s'   │  '1.97 s'   │  '1.97 s'   │  '1.97 s'  │
│    4    │   'Exporting'    │ '28.86 ms'  │ '28.86 ms'  │ '28.86 ms'  │ '28.86 ms' │
└─────────┴──────────────────┴─────────────┴─────────────┴─────────────┴────────────┘
All tasks completed successfully.
```

### Outputs will be in the `output` folder.

```bash
❯ ls output
'erc721 metadata'   images  'sol metadata'
```

#### Sample erc721 metadata:

```json
{
  "description": "This is a token with \"Orange\" as Background",
  "image": "ipfs://__CID__/af5866b14e9567a2fdce9db415e1f55cf9b5dddf.png",
  "name": "Ape 1",
  "dna": "af5866b14e9567a2fdce9db415e1f55cf9b5dddf",
  "uid": "1",
  "generator": "HashLips Lab AE 2.0",
  "attributes": [
    {
      "trait_type": "Background",
      "value": "Orange"
    },
    {
      "trait_type": "Body",
      "value": "Grey"
    },
    {
      "trait_type": "Clothing",
      "value": "Camo"
    },
    {
      "trait_type": "Face",
      "value": "Zap Face"
    },
    {
      "trait_type": "Prop",
      "value": "Backpack"
    }
  ]
}
```

#### Sample solana metadata:

```json
{
  "description": "This is a token with \"Orange\" as Background",
  "image": "ipfs://__CID__/af5866b14e9567a2fdce9db415e1f55cf9b5dddf.png",
  "name": "Ape 1",
  "dna": "af5866b14e9567a2fdce9db415e1f55cf9b5dddf",
  "uid": "1",
  "symbol": "APES",
  "seller_fee_basis_points": 200,
  "generator": "HashLips Lab AE 2.0",
  "attributes": [
    {
      "trait_type": "Background",
      "value": "Orange"
    },
    {
      "trait_type": "Body",
      "value": "Grey"
    },
    {
      "trait_type": "Clothing",
      "value": "Camo"
    },
    {
      "trait_type": "Face",
      "value": "Zap Face"
    },
    {
      "trait_type": "Prop",
      "value": "Backpack"
    }
  ],
  "collection": {
    "name": "The Apes",
    "family": ""
  },
  "creators": [
    {
      "address": "__SOLANA_WALLET_ADDRESS_HERE__",
      "share": 100
    }
  ]
}
```
