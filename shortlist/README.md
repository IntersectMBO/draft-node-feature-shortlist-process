# Shortlist

This directory contains the current shortlist of CIPs approved for implementation across Cardano node implementations.

This corresponds to **step 2: Shortlisting** and **step 3: Candidate Review** in the [process overview](../README.md#overview).

## Files

- **`current-shortlist.md`**: The main shortlist table containing all CIPs currently under consideration (maintained by maintainers)
- **`CIP-XXXX.md`**: Individual detail files for each CIP on the shortlist (one file per CIP)
- **`templates/cip-detail-template.md`**: Template for creating new CIP detail files
- **`archive/implemented.md`**: Historical record of CIPs that have been implemented

## Structure

Each CIP on the shortlist has:
1. **A detail file** (`CIP-XXXX.md`) - Created by proposers via PR, contains in-depth information about the CIP
2. **An entry in the table** (`current-shortlist.md`) - Added by maintainers after PR merge

## Adding a CIP

To add a CIP to the shortlist:
1. Create a new file `CIP-XXXX.md` in this directory using the template
2. Submit a PR with just that file
3. Maintainers will add the CIP to `current-shortlist.md` after merge

See [CONTRIBUTING.md](../CONTRIBUTING.md) for detailed guidelines.

