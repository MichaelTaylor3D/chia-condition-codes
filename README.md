# Readme for Chia Blockchain Conditions

## Installation

Install the package from npm:

```bash
npm install chia-condition-codes
```

## Usage

After installation, you can import the enum into your project:

```javascript
const { ConditionCodes } = require('chia-condition-codes');

OR

import { ConditionCodes } from 'chia-condition-codes';
```

Use the enum in your code like so:

```javascript
const solution = Program.fromSource(`(${ConditionCodes.CREATE_COIN} 300000 (${hint} ${memos.join(" ")}))`);
```

## Conditions Enum

The package exports an enumeration of various conditions used in the Chia blockchain. Each condition represents a specific rule or requirement in Chia's smart contract programming:

- `REMARK`: Always valid. No parameters.
- `AGG_SIG_PARENT`: Verifies a signature with the parent coin id. Part of CHIP-0011.
- `AGG_SIG_PUZZLE`: Verifies a signature with the puzzle hash. Part of CHIP-0011.
- `AGG_SIG_AMOUNT`: Verifies a signature with the amount of the coin.
- `AGG_SIG_PUZZLE_AMOUNT`: Signature verification with puzzle hash and amount.
- `AGG_SIG_PARENT_AMOUNT`: Signature verification with parent coin id and amount.
- `AGG_SIG_PARENT_PUZZLE`: Signature verification with parent coin id and puzzle hash.
- `AGG_SIG_UNSAFE`: Basic signature verification without domain strings.
- `AGG_SIG_ME`: Verifies a signature with the coin id.
- `CREATE_COIN`: Creates a new coin output.
- `RESERVE_FEE`: Ensures minimum fee is reserved.
- `CREATE_COIN_ANNOUNCEMENT`: Creates a coin announcement.
- `ASSERT_COIN_ANNOUNCEMENT`: Asserts a coin announcement.
- `CREATE_PUZZLE_ANNOUNCEMENT`: Creates a puzzle announcement.
- `ASSERT_PUZZLE_ANNOUNCEMENT`: Asserts a puzzle announcement.
- `ASSERT_CONCURRENT_SPEND`: Asserts concurrent spending of a coin.
- `ASSERT_CONCURRENT_PUZZLE`: Asserts spending in the same block with a specific puzzle hash.
- `ASSERT_MY_COIN_ID`: Asserts the coin's id.
- `ASSERT_MY_PARENT_ID`: Asserts the coin's parent id.
- `ASSERT_MY_PUZZLE_HASH`: Asserts the coin's puzzle hash.
- `ASSERT_MY_AMOUNT`: Asserts the coin's amount.
- `ASSERT_MY_BIRTH_SECONDS`: Asserts the coin's creation time in seconds.
- `ASSERT_MY_BIRTH_HEIGHT`: Asserts the coin's creation block height.
- `ASSERT_EPHEMERAL`: Asserts the coin's creation within the current block.
- `ASSERT_SECONDS_RELATIVE`: Asserts the time passed since the coin's creation.
- `ASSERT_SECONDS_ABSOLUTE`: Asserts a specific timestamp.
- `ASSERT_HEIGHT_RELATIVE`: Asserts the block height passed since the coin's creation.
- `ASSERT_HEIGHT_ABSOLUTE`: Asserts a specific block height.
- `ASSERT_BEFORE_SECONDS_RELATIVE`: Asserts a time before a relative timestamp.
- `ASSERT_BEFORE_SECONDS_ABSOLUTE`: Asserts a time before an absolute timestamp.
- `ASSERT_BEFORE_HEIGHT_RELATIVE`: Asserts a block height before a relative height.
- `ASSERT_BEFORE_HEIGHT_ABSOLUTE`: Asserts a block height before an absolute height.
- `SOFTFORK`: Allows for future conditions as soft forks.

For complete documentation on all conditions, please refer to [Chia Blockchain Conditions Documentation](https://docs.chia.net/conditions/).

