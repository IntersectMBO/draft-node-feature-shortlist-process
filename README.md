# Draft Cardano Node Shortlist Process

This was inspired by suggestions from @KtorZ and discussions had via Hard Fork working group call.

> Note:
> This is drafted here for now
> intention is to iterate on this and move the process somewhere else

This repository serves as the central hub for the process to maintain a shortlist of CIPs approved for implementation across Cardano node implementations.

It attempts to ensure alignment on core compatibility across Ledger, Consensus, Plutus, and Networking components.
*And maybe some non-functional requirements*

## Motivation: Why do we need a process?

Historically, there has been a single Cardano node implementation with features/changes managed centrally.

Cardano now has multiple Cardano node implementations, necessitating alignment on core capabilities. Furthermore Cardano now has an on-chain government who is able to make decisions.

Future decisions on Cardano node features/changes (defined via CIPs), must be managed with all stakeholders considered.

### Aims of process

1. **Ensure Alignment**: Coordinate implementation priorities across all Cardano node implementations to maintain core compatibility in Ledger, Consensus, Plutus, and Networking components

2. **Enable Transparency**: Provide an open, transparent process where any Cardano stakeholder can propose CIPs for shortlisting and track their progress through implementation

3. **Utilize Cardano Governance**: Connect technical prioritization with Cardano's on-chain governance

4. **Maintain Quality**: Ensure that shortlisted CIPs are properly evaluated, wanted, needed, documented, and tracked through their implementation lifecycle

5. **Provide clear direction**: Allow node implementors and Cardano stakeholders to see future features/changes allowing for planning and budgeting.

6. **Help packaging/planning for hard forks**:

## Overview

The proposed process for managing node feature implementation is:

0. **CPS Approval**: A CPS is optionally written, reviewed, and approved as a real problem in the [CIP repository](https://github.com/cardano-foundation/CIPs)

1. **CIP Approval**: A CIP is written, reviewed, and approved as a viable solution (to a CPS) in the [CIP repository](https://github.com/cardano-foundation/CIPs)

2. **Shortlisting**: Approved CIPs, which require Cardano Node implementation coordination are proposed as shortlist candidates.

3. **Candidate Review**: Shortlist candidates receive community/stakeholder review and discussion.

4. **Quarterly Review**: The shortlist is periodically created from shortlist candidates revised in node diversity workshops (once per quarter).

5. **Governance Approval**: Once or twice a year, the short list is proposed to DReps for approval (via Ekklesia or on-chain actions). -- maybe something like this?

6. **Budgeting**: Beyond the scope of this process, but with a shortlist implementors are able to plan their implementations and align it with their budget asks.

7. **Implementation**: Build!

8. **Hard fork packaging**: There will be some process aligned with implementation to coordinate hard forks.

This repository proposed to facilitate **step 2** and **step 3**  - maintaining the shortlist of CIPs to implement.

## Repository Structure

```
/
├── README.md                          # This file - repository overview
├── CONTRIBUTING.md                    # Guidelines for making pull requests
├── GOVERNANCE.md                      # Workshop and government approval processes
├── MAINTAINERS.md                     # List of maintainers and their responsibilities
├── shortlist/
│   ├── README.md                      # Shortlist overview and status
│   ├── current-shortlist.md           # Single unified shortlist table (maintained by maintainers)
│   ├── CIP-XXXX.md                    # Individual detail files for each CIP (one per CIP)
│   ├── templates/
│   │   └── cip-detail-template.md     # Template for creating CIP detail files
│   └── archive/
│       └── implemented.md             # Historical record of implemented CIPs
├── workshops/
│   ├── README.md                      # Workshop process documentation
│   └── [YYYY-QX].md                   # Quarterly workshop notes
│
└── .github/
    ├── ISSUE_TEMPLATE/
    │   └── cip-proposal.md            # Template for proposing CIP addition
    ├── pull_request_template.md       # PR template for adding CIPs
    └── workflows/
        └── validate-shortlist.yml     # CI workflow to validate format
```

## Shortlist Format

The shortlist consists of two parts:

### 1. Shortlist Candidate CIP Files (`shortlist/CIP-XXXX.md`)

Each CIP has its own detail file created by proposers.
These files contain in-depth information including:

- **Hard fork Required**: Yes | No | Unknown (with explanation)
- **Need new Ledger era?**: Yes | No | Unknown (with explanation)
- **Impact Areas**: Which node components are affected (with detailed explanation)
- **Dependencies**: Links to other CIPs this depends on (with explanations)
- **Rationale**: Why this CIP should be shortlisted
- **Additional Context**: Any other relevant information

### 2. Shortlist Table (`shortlist/current-shortlist.md`)

The main shortlist table is maintained by maintainers and contains:

- **CIP Number**: Link to CIP repository
- **Title**: CIP title
- **Category**: Ledger | Consensus | Plutus | Networking | Cross-cutting
- **Hard fork Required**: Yes | No | Unknown
- **Need new Ledger era?**: Yes | No | Unknown
- **Status**: Proposed | Under Review | Approved for Implementation | In Progress | Implemented
- **Priority**: High | Medium | Low (updated during workshops)
- **Rank**: Numerical rank (1-N, updated quarterly)
- **Dependencies**: Links to other CIPs this depends on
- **Impact Areas**: Which node components are affected
- **Added Date**: When CIP was added to shortlist
- **Last Reviewed**: Date of last workshop review
- **Notes**: Brief rationale or key considerations

**Note**: Proposers create the detail file (`CIP-XXXX.md`).
Maintainers add entries to the table (`current-shortlist.md`) after discussions are had and PR is merged.

## How to Contribute

**Anyone can contribute** by submitting a pull request to add a CIP to the shortlist.

### Process

1. **Fork and Create PR**: Fork this repository and create a pull request adding a CIP to `shortlist/current-shortlist.md`

2. **Create CIP Detail File**: Create a new file `shortlist/CIP-XXXX.md` with detailed information about the CIP. Use the template at `shortlist/templates/cip-detail-template.md` as a guide. Your file must include:
   - CIP number and link to the approved CIP (must be approved in CIP repository)
   - Hard fork requirement assessment (Yes/No/Unknown) with explanation
   - Need new Ledger era? assessment (Yes/No/Unknown) with explanation
   - Impact areas with detailed explanation
   - Dependencies with explanations
   - Rationale for why the CIP should be shortlisted

3. **Community Discussion** (step 3: Candidate Review): Consensus from key stakeholders is shown via discussions in PR comments or the GitHub Discussions tab

4. **Maintainer Review**: Independent maintainers review the PR for format compliance and completeness

5. **Merge**: Maintainers merge PRs that meet requirements after discussion

6. **Table Update**: After merge, maintainers add the CIP to `current-shortlist.md` table

7. **Workshop Inclusion**: Merged CIPs are included in the next quarterly workshop review (see **step 4: Quarterly Review**)

## Maintainers

Independent maintainers ensure the process continues smoothly:

- **Review PRs**: Review and merge pull requests that add CIPs to the shortlist
- **Maintain Quality**: Ensure shortlist entries are complete and properly formatted
- **Facilitate Workshops**: Organize and document quarterly node diversity workshops (step 4: Quarterly Review)
- **Update Rankings**: Update rankings based on workshop outcomes
- **Prepare DRep Submissions**: Compile shortlist for annual/bi-annual DRep approval (step 5: Governance Approval)
- **Process Maintenance**: Keep documentation up-to-date and process running smoothly

Maintainers do not gatekeep which CIPs can be added—they ensure the process is followed correctly.

The community decides what gets shortlisted through the open PR process.
