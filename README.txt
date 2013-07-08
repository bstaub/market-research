Coursera market-research code review :-)
########################################

08.07.2013, STBR

Howto install
-------------

# Download and make executable
  wget https://spark-public.s3.amazonaws.com/startup/code/market-research.js
  wget https://spark-public.s3.amazonaws.com/startup/code/market-research-wrapper.js
 
# Install npm dependencies. This will create a node_modules directory in
# the current working directory. Don't cd into other directories right
# now; later we'll show how to install modules globally.
  npm install restler csv accounting
 
# As a script
  node market-research.js 
  node market-research.js FB ORCL
 
# As an executable
  chmod 777 market-research.js 
  ./market-research.js 
  ./market-research.js GOOG CRM
 
# As a module, through another program invoked as a script
  node market-research-wrapper.js
 
# As a module, through another program being invoked as an executable
  chmod 777 market-research-wrapper.js
  ./market-research-wrapper.js
 
# Also as a module - but with the external code being input at the command line
# via the -e flag
  node -e "require('./market-research.js')"
  node -e "var mr = require('./market-research.js'); mr.marketResearch();"
  node -e "var mr = require('./market-research.js'); mr.marketResearch([\"FB\",\"ORCL\"]);"

Howto Submit GitHub
-------------------
0:
create empty github repo with name: market-research
and copy instruction (see 3:)

1:
ssh-keygen -t rsa -C "bruno.staub@intersolution.ch"

2:
copy output from public rsa key to github --> SSH Keys
cat .ssh/id_rsa.pub 

3:
#optional start
git config --global user.name "Bruno Staub"
git config --global user.email bruno.staub@intersolution.ch
git commit --amend --reset-author
#optional end
touch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:bstaub/market-research.git
#require public rsa key in github
git push -u origin master
#requre end
