# Level Finance Exploit PoC — Referral Reward Claim Logic Error

## Overview
- **Date:** 2023-05-01
- **Loss:** ~$1.1M
- **Chain:** BSC
- **Category:** Logic / Math Errors
- **Block:** 27835718

## Vulnerability
Level Finance's referral reward claim function did not mark rewards as claimed after distribution. The attacker could call claimMultiple() repeatedly for the same epochs, receiving the full reward amount each time.

## Reproduction
```bash
git clone https://github.com/NomosLabs-Security/poc-level-finance-2023
cd poc-level-finance-2023
forge install foundry-rs/forge-std --no-git
forge test -vvvv
```

## References
- [Level Finance Post-Mortem](https://levelfinance.medium.com/post-mortem-on-referral-controller-exploit-7f78a5a2ec3c)
