# How to Use Threshold AI Bug Hunter

## 🚀 Running the Workflow

### Option 1: Manual Trigger (Recommended for Testing)

1. Go to your repository: https://github.com/nayakvishal6911-art/threshold-ai-bug-hunter
2. Click **Actions** tab
3. Select **"Threshold AI Bug Hunter"** from the left sidebar
4. Click **"Run workflow"** button
5. Choose branch: **main**
6. Click **"Run workflow"**

### Option 2: Automatic Schedule

The workflow runs automatically every day at:
- **04:17 UTC** (Greenwich Mean Time)
- **09:47 IST** (Indian Standard Time)

No action needed - it runs on its own schedule!

## 📊 Viewing Results

### During Execution
1. Go to **Actions** tab
2. Click the active workflow run
3. Watch real-time logs for each step

### After Completion
1. Scroll down to **Artifacts** section
2. Download **threshold-ai-bug-hunt** (contains all findings)

### Reviewing Findings
Extract the downloaded artifact and review:
- `semgrep.json` - Automated scanner results
- `security-surface.md` - Pattern matching findings
- `history.md` - Security-related git history
- `candidate-index.md` - Indexed candidates
- `BOUNTY_VALIDATION.md` - Validation checklist
- `STATUS.md` - Completion status

## ✅ What the Workflow Does

```
┌─────────────────────────────────────┐
│ Clone Threshold tBTC Repository     │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│ Run Semgrep Smart Contract Analysis │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│ Security Pattern Surface Scanning   │
│  - Authorization                    │
│  - External Calls                   │
│  - Signatures                       │
│  - Accounting                       │
│  - Bridges                          │
│  - Time Dependencies                │
│  - Low-level Solidity               │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│ Historical Security Analysis        │
│  - Security commits                 │
│  - Recent changes                   │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│ Generate Reports & Artifacts        │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│ Upload & Retention (14 days)        │
└─────────────────────────────────────┘
```

## 🛡️ Safety & Disclaimers

✅ **Safe Operations:**
- No mainnet exploitation
- No public-testnet exploitation
- No wallet required
- No real money spent
- No automatic Immunefi submission

⚠️ **Important:**
- Scanner findings are candidates ONLY
- Manual validation required
- PoC reproduction required
- Project confirmation required before bounty claim
- No guarantee of bounty

## 📈 Workflow Performance

- **Duration**: ~5-10 minutes typical
- **Timeout**: 40 minutes maximum
- **Concurrency**: Single run (cancels previous)
- **Frequency**: Daily + manual triggers
- **Artifact Retention**: 14 days

## 🔧 Customization

To modify the workflow:
1. Go to `.github/workflows/threshold-bug-hunter.yml`
2. Edit the file
3. Commit changes
4. Workflow updates automatically

Common modifications:
- Change schedule (cron expression)
- Add/remove security patterns
- Adjust grep head limits
- Modify analysis sections

## 📞 Troubleshooting

### Workflow Not Running
- Check Actions are enabled in Settings
- Verify cron schedule
- Ensure `.github/workflows/` directory exists

### No Artifacts Generated
- Check workflow logs for errors
- Verify target repository is accessible
- Check Semgrep installation

### Analysis Missing Results
- Some patterns may have no matches (normal)
- Check `|| true` prevents failures on no matches
- Review logs for any grep errors

## 📚 References

- Workflow File: `.github/workflows/threshold-bug-hunter.yml`
- Configuration: `WORKFLOW_CONFIG.md`
- Repository: https://github.com/nayakvishal6911-art/threshold-ai-bug-hunter
- Target: https://github.com/threshold-network/tbtc-v2

---

**Status**: ✅ Ready to Hunt | **Last Updated**: 2026-09-11
