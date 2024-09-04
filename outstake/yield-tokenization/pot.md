---
description: Position Option Token
---

# POT

POT (Position Options Token) represents the right to redeem a position upon maturity. When a user stakes and locks native yield assets, in addition to minting PT and YT, a POT is also minted to encapsulate the user's position.

POT allows holders to burn a fixed amount of PT in the future, when the position lock-up period expires, to redeem a fixed amount of Native Yield Tokens. By trading POT, user can trade the right to obtain a fixed interest rate without needing to trade PT itself.

POT is supported by the [ERC1155](https://eips.ethereum.org/EIPS/eip-1155) standard and divides the position into shares equal to the number of PTs minted, allowing users to trade partial redemption rights of their positions.
