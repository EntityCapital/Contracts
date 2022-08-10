# Contracts

## Entity.sol

The main smart contract currently in use, deployed to 0xeef6020b7720f4e000476b017fc4e224dfc0aa36 on Binance Smart Chain.

## Erratum regarding variable taxes

- Contrary to what has been mentioned on several rugcheck websites (i.e. staysafu.org or tokensniffer.com) and on coingecko.com, the fees are hardcoded in the contract, and thus cannot be edited afterward. So we cannot change tax rates post deployment. You can find the relevant part of the code below (lines 459 to 470):

```
uint256 public liquidityFee = 20;
    uint256 public treasuryFee = 10;
    uint256 public entityInsuranceFundFee = 20;
    uint256 public sellFee = 10;
    uint256 public blackholeFee = 10;
    uint256 public lotteryFee = 5;
    uint256 public foundationFee = 10;
    uint256 public tipFee = 5;
    uint256 public totalFee =
        liquidityFee.add(treasuryFee).add(entityInsuranceFundFee
        //).add(blackholeFee).add(foundationFee).add(tipFee).add(lotteryFee
        );
```
The fees being static/fixed ensure that no one can edit them afterwards, hence there no flaw regarding a variable tax into this contract.

## Links

- Website: https://entity.capital
- Documentation: https://help.entity.capital
- Smart contract: https://bscscan.com/address/0xeef6020b7720f4e000476b017fc4e224dfc0aa36#code
