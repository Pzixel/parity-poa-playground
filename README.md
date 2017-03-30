# parity-playground

0. Run `git clone github.com:dstarcev/parity-poa-playground.git && cd parity-poa-playground`
1. `docker-compose up`
2. Run `docker-compose logs | grep token=` to get an authenticated URL for the Parity UI.
Yoy will need to copy the authentication token from the output of the previous command to log in.
3. Navigate to [http://127.0.0.1:3001](http://127.0.0.1:3001) for the [ethstats](https://github.com/cubedro/eth-netstats) dashboard.
4. Talk to JSON RPC at [http://127.0.0.1:8545](http://127.0.0.1:8545) with your favorite client.

You may also want to change the list of prefunded accounts in `parity/chain.json`.

There is already one with an empty password that has enough ether:

```
0x6B0c56d1Ad5144b4d37fa6e27DC9afd5C2435c3B
```

And one who is broke:
```
0x00E3d1Aa965aAfd61217635E5f99f7c1e567978f
```

Be kind and send the poor an ether!

```
curl --data '{"jsonrpc":"2.0","method":"personal_sendTransaction","params":[{"from":"0x6B0c56d1Ad5144b4d37fa6e27DC9afd5C2435c3B","to":"0x00E3d1Aa965aAfd61217635E5f99f7c1e567978f","value":"0xde0b6b3a7640000"}, ""],"id":0}' -H "Content-Type: application/json" -X POST localhost:8545
```
