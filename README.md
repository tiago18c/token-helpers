# solana-token

A set of helpers and wrappers around multiple Solana token libraries that enable developers to create token accounts with one-liners, supporting different token standards including Token Program (TokenKeg), Token-2022, and Token-ACL.

## Features

- **Multi-standard support**: Automatically detects and handles Token Program, Token-2022, and Token-ACL mints
- **One-liner API**: Simple functions to create associated token accounts without manual instruction building
- **Automatic handling**: Handles Token-ACL specific requirements (e.g., thaw instructions) automatically

## Installation

```bash
npm install solana-token
# or
pnpm add solana-token
```

## Usage

### Create and Confirm Associated Token Account

```typescript
import { createAndConfirmAssociatedTokenAccount } from 'solana-token';

const { signature, associatedTokenAddress } = await createAndConfirmAssociatedTokenAccount(
  rpc,
  rpcSubscriptions,
  payer,
  owner,
  mintAddress
);
```

### Create Associated Token Account (without confirmation)

```typescript
import { createAssociatedTokenAccount } from 'solana-token';

const { signature, associatedTokenAddress } = await createAssociatedTokenAccount(
  rpc,
  payer,
  owner,
  mintAddress
);
```

### Get Instructions Only

```typescript
import { createAssociatedTokenAccountInstructions } from 'solana-token';

const { instructions, associatedTokenAddress } = await createAssociatedTokenAccountInstructions(
  rpc,
  payer,
  owner,
  mintAddress
);
```