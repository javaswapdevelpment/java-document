---
description: JavaSwap's Contracts
---

# Contracts

Our contracts are publicly accessible in the following repo [github.com/javaswapdevelpmentjava-contracts](https://github.com/javaswapdevelpment/java-contracts)

- **JAVA:** [0x2849b1aE7E04A3D9Bc288673A92477CF63F28aF4](https://bscscan.com/address/0x2849b1aE7E04A3D9Bc288673A92477CF63F28aF4)
- **MasterChef:** [0xB4405445fFAcF2B86BC2bD7D1C874AC739265658](https://bscscan.com/address/0xB4405445fFAcF2B86BC2bD7D1C874AC739265658)
- **Timelock:** [0xB5cD51B879424a920513a66407BB041a9E904731](https://bscscan.com/address/0xB5cD51B879424a920513a66407BB041a9E904731) (delay: 24h)

**How are our contracts safe?**

We have based our implementation in Goose Finance's EGG token and have the following features:

- **24h** timelock added to contract at launch;
- No migrator code, it was totally removed;
- Contract audit in the pipeline.

**Removed migratator code**

Removed from PancakeSwap's [MasterChef.sol](https://github.com/pancakeswap/pancake-farm/blob/master/contracts/MasterChef.sol)

```javascript
// Set the migrator contract. Can only be called by the owner.
function setMigrator(IMigratorChef _migrator) public onlyOwner {
    migrator = _migrator;
}

// Migrate lp token to another lp contract. Can be called by anyone. We trust that migrator contract is good.
function migrate(uint256 _pid) public {
    require(address(migrator) != address(0), "migrate: no migrator");
    PoolInfo storage pool = poolInfo[_pid];
    IBEP20 lpToken = pool.lpToken;
    uint256 bal = lpToken.balanceOf(address(this));
    lpToken.safeApprove(address(migrator), bal);
    IBEP20 newLpToken = migrator.migrate(lpToken);
    require(bal == newLpToken.balanceOf(address(this)), "migrate: bad");
    pool.lpToken = newLpToken;
}
```

**Diff EGG MasterChef vs JAVA MasterChef**

Please refer to the following diffchecker: [diffchecker.com/AoYdXp6H](https://www.diffchecker.com/AoYdXp6H)
