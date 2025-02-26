# HAQQ Balance Checker

Preview on [igroza.github.io/haqq-cosmos-balances](https://igroza.github.io/haqq-cosmos-balances)

> You can also use the query `?address=<address>` to directly get the balance of a specific address
> [igroza.github.io/haqq-cosmos-balances?address=0xF015a66078c6a7642063e0353f45F5244280AdAf](https://igroza.github.io/haqq-cosmos-balances?address=0xF015a66078c6a7642063e0353f45F5244280AdAf)

## Fields

| Name                  | Value                                              | Comment                                                                             |
| --------------------- | -------------------------------------------------- | ----------------------------------------------------------------------------------- |
| available_for_stake   | cosmos/bank/v1beta1/balances/                      | Total balance - amount available for staking                                        |
| available             | cosmos/bank/v1beta1/spendable_balances             | Balance available for spending                                                      |
| staked                | cosmos/staking/v1beta1/delegations                 | All user stakes                                                                     |
| unbonding             | cosmos/staking/v1beta1/delegators/../unbonding     | Tokens in the unbonding pool                                                        |
| rewards | cosmos/distribution/v1beta1/delegators/XXX/rewards | Staking rewards not yet collected                                                   |
| total_locked          | haqq/vesting/v1/balances/ -> locked                | All user locked tokens                                                              |
| vested                | available_for_stake - available                    | Locked, on balance                                                                  |
| staked_vested         | total_locked - vested                              | Locked, in staking                                                                  |
| total_staked          | staked + unbonding + rewards                       | All user tokens involved in staking and not on their balance                        |
| staked_free           | total_staked - staked_vested                       | Freely staked coins                                                                 |
| DAO_locked    | /haqq/dao/v1/balances/                             | Sum of all user tokens aISLM and aLIQUIDXXX 1 to 1  |
| locked                | total_staked + vested + DAO_locked                 | All locked tokens schedule + staking                                                |
| total                 | available_for_stake + total_staked                 | Total user balance                                                                  |
