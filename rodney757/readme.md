`multisig_wallets.csv` was generated using the script found in this directory.

`multisig_wallets_filtered.csv` is a filtered view of `multisig_wallets.csv` including only the address containg eth and/or 
tokens. Theses addresses were filtered using BokkyPoobah's provided [`ethers.csv`](https://github.com/Giveth/WHGBalanceVerification/blob/master/BokkyPoobah/ethers.csv)
and [`tokens.csv`](https://github.com/Giveth/WHGBalanceVerification/blob/master/BokkyPoobah/tokens.csv) data.

### multisig_wallets.csv -> multisig_wallets.csv.array

`cp multisig_wallets.csv multisig_wallets.csv.array`

`vim multisig_wallets.csv.array`

`:%s/^/\[/g`

`:%s/$/]/g`

`:wq`


### cleanup of multisig_wallets_filtered.csv for easy comparison

`vim multisig_wallets_filtered.csv`

`:%s/^\[//g`

`:%s/]$//g`

manually remove python appended `L` suffix from `dayLimit` values where needed

### discrepancy note

There is 1 additional address found in jbaylina's data that mine does not include. This was a contract that was created in the middle of the rescue. My script fetched contract
data from before the attack. jbaylina manually handled the special case of this address in his script. The address is `0xdf86984226814e2970ea94fedd9676276fedfacb`


