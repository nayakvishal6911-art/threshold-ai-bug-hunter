# Threshold AI Bug Hunter

Automated security research and bug hunting workflow for Threshold tBTC smart contracts.

## 🤖 Overview

This repository contains an automated GitHub Actions workflow that performs daily security analysis on the Threshold tBTC smart contracts, including:

- **Semgrep Static Analysis** - Detects common smart contract vulnerabilities
- **Security Surface Scanning** - Pattern matching for authorization, external calls, signatures, accounting, bridges, time-dependencies, and low-level Solidity
- **Historical Analysis** - Tracks security-related commits and Solidity changes
- **Bounty Validation** - Comprehensive checklist to validate findings before reporting

## 🔄 Workflow Schedule

- **Manual Trigger**: Anytime via `workflow_dispatch`
- **Automatic Schedule**: Daily at 04:17 UTC (09:47 IST)

## 📊 Workflow Steps

1. Clone Threshold tBTC repository
2. Record target revision and recent commits
3. Install Semgrep analysis tool
4. Run Semgrep smart contract rules
5. Security surface scan for critical patterns
6. Historical security analysis
7. Build known issues filter
8. Build candidate index
9. Create validation checklist
10. Generate status report
11. Bundle and upload artifacts

## 🛡️ Safety Features

- ✅ No mainnet exploitation
- ✅ No public-testnet exploitation
- ✅ No wallet required
- ✅ No money spent
- ✅ No automatic Immunefi submission
- ✅ Manual validation required before any bounty claim

## 📦 Artifacts

All findings are packaged and retained for 14 days:
- `semgrep.json` - Semgrep scan results
- `security-surface.md` - Pattern matching findings
- `history.md` - Security-related git history
- `known-issues.md` - Excluded issue categories
- `candidate-index.md` - Indexed findings
- `BOUNTY_VALIDATION.md` - Validation checklist
- `STATUS.md` - Run status report
- `target.txt` - Target revision info
- `threshold-research.tar.gz` - Complete bundle

## ⚠️ Important

A scanner finding is **NOT automatically a bounty**. Any candidate must be:
- Manually validated
- Reproduced locally
- Confirmed by the project/Immunefi
- Paid before claiming success

## 🚀 Getting Started

1. Navigate to the **Actions** tab
2. Select "Threshold AI Bug Hunter"
3. Click "Run workflow"
4. Monitor the execution
5. Download artifacts after completion

## 📝 License

This project is for educational and authorized security research purposes only.
