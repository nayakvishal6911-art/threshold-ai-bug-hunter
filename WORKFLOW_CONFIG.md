# Threshold AI Bug Hunter - Configuration

## Workflow Configuration

### Schedule
- **Cron**: `17 4 * * *` (04:17 UTC daily, 09:47 IST)
- **Manual Trigger**: Enabled via `workflow_dispatch`

### Environment
- **Runner**: `ubuntu-latest`
- **Timeout**: 40 minutes
- **Concurrency**: Single concurrent run (cancels previous in-progress runs)

### Permissions
- `contents: read` - Read-only access to repository contents

## Analysis Sections

### 1. Authorization Patterns
Scans for:
- `onlyOwner`, `onlyBridge`, `onlyRole`, `hasRole`
- `msg.sender`, `_msgSender`

### 2. External Calls
Scans for:
- `delegatecall`, `call{`, `staticcall`
- `transferFrom`, `safeTransferFrom`

### 3. Signature & Authentication
Scans for:
- `ecrecover`, `ECDSA`, `permit`
- `signature`, `nonce`

### 4. Accounting
Scans for:
- `mint`, `burn`, `balanceOf`, `allowance`
- `increaseBalance`, `decreaseBalance`

### 5. Bridge / Cross-chain
Scans for:
- `Wormhole`, `Gateway`, `Bridge`
- `receiveTbtc`, `sendTbtc`, `completeTransfer`, `deposit`

### 6. Time / Block Dependencies
Scans for:
- `block.timestamp`, `block.number`, `blockhash`

### 7. Low-level Solidity
Scans for:
- `assembly`, `unchecked`, `selfdestruct`

## Output Artifacts

All findings are stored in the `findings/` directory and packaged as `threshold-research.tar.gz`:

- **semgrep.json**: Machine-readable Semgrep results
- **security-surface.md**: Human-readable pattern matching results
- **history.md**: Git history analysis
- **candidate-index.md**: Indexed findings by category
- **known-issues.md**: Exclusion criteria
- **BOUNTY_VALIDATION.md**: Validation checklist
- **STATUS.md**: Run status and safety information
- **target.txt**: Target revision and recent commits

## Retention Policy

- Artifacts retained for **14 days**
- Automatic cleanup after retention period

## GitHub Summary

Workflow writes completion status to GitHub Actions summary including:
- Research completion status
- Safety verification
- Important bounty disclaimers
