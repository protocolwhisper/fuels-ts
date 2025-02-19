# Transaction parameters

Transaction parameters are:

1. Gas price;
2. Gas limit;
3. Maturity.

You can configure these parameters by using the optional `TxParams` and passing it to a chain method called `txParams`:

<<< @/../../../packages/fuel-gauge/src/contract.test.ts#Contract-tx-params{ts:line-numbers}

If you do not pass the `TxParams`, the values default to those of the chainConfig provided to your Fuel node.

As you might have noticed already, `TxParams` can also be specified when deploying contracts or transferring assets by passing it to the respective methods.

> **Note:** whenever you perform an action that results in a transaction (contract deployment, contract call, asset transfer), the SDK will automatically estimate the fee based on the set gas limit and the transaction's byte size. This estimation is used when building the transaction. A side-effect of this is that your wallet must at least own a single coin of the base asset of any amount.
