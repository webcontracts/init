<div align="center">
  <h1>Init</h1>
</div>

<div align="center">  
<i>Web Contract to init a ledger</i>
</div>

---

<div align="center">
<h4>Documentation</h4>
</div>
  
---
  
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/webcontracts/init/blob/gh-pages/LICENSE)
[![npm](https://img.shields.io/npm/v/webcontract-init)](https://npmjs.com/package/webcontract-init)
[![npm](https://img.shields.io/npm/dw/webcontract-init.svg)](https://npmjs.com/package/webcontract-init)
[![Github Stars](https://img.shields.io/github/stars/webcontracts/init.svg)](https://github.com/webcontracts/init/)
  
# ⚡️ Introduction

Init is a web contract to init a ledger

# Data Model

## Web Credit

Here is a full example of a [Web Credits](https://webcredits.org/) Object

```
{
  "@id": "urn:cuid:a74xt3jbin",
  "@type": "Credit",
  "source": "https://melvincarvalho.com/#me"
  "amount": 100,
  "currency": "Mark",
  "destination": "http://webr3.org/nathan#me",
  "description": "for technical help",
  "context": "https://github.com/project-bitmark/bitmark",
  "timestamp": 1640111035
}
```

## Web Ledger

A [web ledger](https://webledgers.org/) in this case can be derived from the credit object

Both the webledger and the web credits will appear as JSON in the `webcredits` directory, which is in the `.gitignore` so that it can be a separate entity

## Web Contract

The Web Contract is a single file that operates on the webcredits data store and is described [here](https://github.com/webcontracts/init/blob/gh-pages/webcontracts/init.js)

## Signing

Currently signing is done out of band using the [gitmark](https://git-mark.com/) protocol, but explicit signing will be added, in future

# ✍️ API

```
init.js
```

The following switches are allowed
```
--id          # the id for the wallet object
--currency    # the currency
--walletFile  # the wallet file
--creditFile  # the webcredits file
--ledgerFile  # the webledgers file
--indir       # the webcredits directory, defaults to ./webcredits
```

or from npm 

```JavaScript
import init from 'webcontracts-init'

var wallet = {
  id: data.id,
  currency: data.currency
}

function init(wallet, indir, walletFile, ledgerFile, creditsFile)
```

indir, infile, walletFile, ledgerFile and creditsFile are optional and will default to `../webcredits/webcredits.json`


# ⚖️ License

- MIT
