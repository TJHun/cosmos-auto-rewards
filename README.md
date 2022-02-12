## Osmosis automatic rewards and stake

The provided script enable delegators to claim all their staking rewards and reinvest them, to receive compounded interest.

There is no requirement to run a local full node as the script defaults to using the https://rpc-osmosis.itastakers.com:443 RPC endpoint.


### Installation

First download the script and make it executable:
```
curl -O https://raw.githubusercontent.com/TJHun/osmosis-auto-rewards/master/osmosis-auto-rewards.sh
chmod +x osmosis-auto-rewards.sh
```

### Enjoy the show

The script has some default settings and only requires you to provide the name for the account you wish to work with.

The name must match the output of the NAME: column of `gaiad keys list`:  
![keychain](https://validator.network/img/gaiacli01.png "gaiad keys list output")

You can now run the script:
```
./osmosis-auto-rewards.sh testkey1 XxpasswordxX
```

and expect output such as:

```
======================================================
Account: testkey1 (local)
Address: cosmos1mjgh0rejtljxg8rurmxlrff0kk2ztxmgc8mvzj
======================================================
Account balance:   20000122217uatom
Available rewards: 23588169uatom
Net balance:       20023710386uatom
Reservation:       100000000uatom

You are about to delegate 19923710386uatom to cosmosvaloper1sxx9mszve0gaedz5ld7qdkjkfv8z992ax69k08:
  Moniker: Validator🌐Network
  Details: Highly resilient and secure validator operating out of Northern Europe. See website for terms of service.
```

### Customize settings (optional)
If you like, you can use your favorite text editor to change some of the default settings of the script.

```
##############################################################################
# User settings.
##############################################################################

MINIMUM_DELEGATION_AMOUNT="2000000"
RESERVATION_AMOUNT="100000"
VALIDATOR="cosmosvaloper1sxx9mszve0gaedz5ld7qdkjkfv8z992ax69k08"

##############################################################################
```

Take care to specify the `RESERVATION_AMOUNT` which is the minimum amount of uatoms that will remain available in your account.

You can delegate to any validator you prefer by changing `VALIDATOR` variable.
