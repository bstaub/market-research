Coursera market-research code review :-)
########################################

08.07.2013, STBR

Howto install
-------------

Download and make executable:
```bash
  wget https://spark-public.s3.amazonaws.com/startup/code/market-research.js
  wget https://spark-public.s3.amazonaws.com/startup/code/market-research-wrapper.js
```

* Install npm dependencies. This will create a node_modules directory in
* the current working directory. Don't cd into other directories right
* now; later we'll show how to install modules globally.

```bash
  npm install restler csv accounting
```

As a script:
```bash
  node market-research.js 
  node market-research.js FB ORCL
```

As an executable:
```bash
  chmod 777 market-research.js 
  ./market-research.js 
  ./market-research.js GOOG CRM
```
 
As a module, through another program invoked as a script:
```bash
  node market-research-wrapper.js
```
 
As a module, through another program being invoked as an executable
```bash
  chmod 777 market-research-wrapper.js
  ./market-research-wrapper.js
```
 
* Also as a module - but with the external code being input at the command line
* via the -e flag

```bash
  node -e "require('./market-research.js')"
  node -e "var mr = require('./market-research.js'); mr.marketResearch();"
  node -e "var mr = require('./market-research.js'); mr.marketResearch([\"FB\",\"ORCL\"]);"
```
