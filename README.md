# Hardhat Ignition Template

Hardhat ignition template with custom The number of confirmations Hardhat Ignition waits before considering a transaction as complete

* **Issue**
`You have sent transactions from 0x... and they interfere with Hardhat Ignition. Please wait until they get 5 confirmations before running Hardhat Ignition again.`

* **My solution** is set `requiredConfirmations` to `1` (cannot be less than 1)
```ts
const config: HardhatUserConfig = {
  solidity: ...,

  ignition: {
    requiredConfirmations: 1
  },
};
```

More info about [Ignition configuration](https://github.com/NomicFoundation/hardhat/blob/main/docs/src/content/ignition/docs/config/index.md)

----

If you want to deploy contract without previous execution stored in `.\ignition\deployments...` You can customize the deployment folder name by providing an explicit deployment ID with `--deployment-id <id>`

example

```
npx hardhat ignition deploy ./ignition/modules/Lock.ts  --deployment-id "eth-1-prod"
```

More info about [Deployment guide](https://github.com/NomicFoundation/hardhat/blob/main/docs/src/content/ignition/docs/guides/deploy.md)