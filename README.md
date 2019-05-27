# Masternode-Guide
A simple guide to create masternodes of CBR


# Calibur Coin Masternode Setup Guide (Ubuntu 18.04)
***
## Required
1) **20000 CBR coins**
2) **Local Wallet https://github.com/caliburcoin/Crypto-Calibur/releases**
3) **VPS with UBUNTU 18.04 (1gb ram recommended)** 
4) **Putty https://www.putty.org/**
5) **Text editor on your local pc to save data for copy/paste**
***

***On your Local Wallet*** (step 6)
* Create an address with a label MN1 and send exactly 20000 CBR to it. Wait to complete 6 confirmations on “ Payment to yourself “ created.

(step 7)
* Open the Debug Console ( Tools – Debug Console ) and type ***createmasternodekey***.
You will then receive your private key, save it in a text editor to use it later.
  ```
  Example:
          masternode key
          57eCdGQBaDKHqGsbm1WDVyN1K6WTfCvcpwu1QC1frmMGnfFnhaa


  ```
(step 8)
* Open Debug Console Again and type ***getmasternodeoutputs*** 
and copy txhash and outpidx, save it in a text editor to use it later
```
  Exemple:
          "txhash" : "bf9c0bdc7dfa6a8be8da2680a77cb17e99d1337c3e186563475370c613c19f71",
		         "outputidx" : 0
 ```
***On Putty*** (step 9)

* Once logged in your vps, *copy/past* each line one by one with *Enter*

	:arrow_forward: `apt-get update`

	:arrow_forward: `wget -q https://github.com/caliburcoin/Masternode-Guide/blob/master/caliburmn.sh`
  
  :arrow_forward: `apt-get install -y dos2unix`
  
  :arrow_forward: `dos2unix caliburmn.sh`
  
  :arrow_forward: `bash caliburmn.sh`

(step 10)
* Let this run, after a min it will show you 3 options press 1 and click enter 
it will take few minutes to install dependencies. after that it will ask you to enter your masternode key (step 7) paste and click enter

(step 11)
after pressing enter wait and when installation finish run `systemctl status Calibur` and see if its  active should be like this http://prntscr.com/nswp08

***Go back to your Local Wallet***

* Open the Masternode Configuration file (tools – open masternode configuration file) and add a new line (without #) using this template below 

**ALIAS VPS_IP**:55555 **masternodeprivkey (step 7) TXhash Output (step 8)**

		Example:
		MN1 125.67.32.10:55555 57eCdGQBaDKHqGsbm1WDVyN1K6WTfCvcpwu1QC1frmMGnfFnhaa 
		bf9c0bdc7dfa6a8be8da2680a77cb17e99d1337c3e186563475370c613c19f71 0

* Close and Re-open Local Wallet, and at Masternode Tab you will find your MN with status MISSING

***(For the next steps you need to have already 21 confirmation on “Payment to yourself “ created in first step)***

* Goto Masternode tab and click on start all and clicking you node must show status  enabled

*your CBR node is running if you find any problem please contact us on discord

