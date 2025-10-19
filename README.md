# STX Put Vault Smart Contract

## Overview
A Clarity smart contract implementing cash-settled PUT options on STX with a centralized vault mechanism. Built for Stacks blockchain using Clarity 2.0.

## Features
- 🏦 Vault-backed put options
- 💰 Cash-settled in STX
- 🔒 Secure price oracle integration
- ⚡ Efficient settlement process
- 📊 Flexible strike price and premium settings

## Contract Architecture

### Core Components
1. **Vault Management**
   - Owner-controlled vault funding
   - Secure balance tracking
   - Protected withdrawal mechanism

2. **Option Series**
   - Configurable strike prices
   - Flexible premium settings
   - Time-bound expiry
   - Oracle-based settlement

3. **Position Management**
   - Buy/sell functionality
   - Position tracking
   - Settlement claims

## Usage

### Administrative Functions
```clarity
(set-oracle (who principal))
(fund-vault)
(owner-withdraw (amt uint) (to principal))
```

### Trading Functions
```clarity
(create-series (strike uint) (premium uint) (expiry uint))
(buy (id uint) (quantity uint))
(settle-series (id uint))
(claim (id uint))
```

### View Functions
```clarity
(get-series (id uint))
(get-next-series-id)
(position-of (id uint) (who principal))
(get-vault-balance)
```

## Technical Details
- **Price Scale**: 1 STX = 1,000,000 micro-STX
- **Oracle Integration**: Implements price-oracle trait
- **Settlement**: Cash-settled in STX
- **Platform**: Stacks Blockchain
- **Language**: Clarity 2.0

## Security Considerations
- Owner-controlled vault management
- Protected administrative functions
- Secure balance tracking
- Safe arithmetic operations
- Protected settlement process

## Development
```bash
# Install dependencies
clarinet install

# Run tests
clarinet test

# Deploy contract
clarinet deploy
```

## Testing
Comprehensive test suite available in the tests directory covering:
- Vault operations
- Series creation
- Trading functions
- Settlement process
- Edge cases
---
Built with ❤️ for the Stacks ecosystem
