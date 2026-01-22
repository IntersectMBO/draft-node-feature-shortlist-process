# Abstract

Cardano has evolved from a single node implementation to a multi-implementation ecosystem.

This transition creates a critical coordination challenge: ensuring that Cardano Improvement Proposals (CIPs) requiring node implementation are prioritized, aligned, and implemented consistently across all node implementations.
Without a structured process, there is a risk of fragmentation, incompatible implementations, and misalignment.

This document outlines the need for a transparent, community-driven shortlist process that coordinates implementation priorities across Ledger, Consensus, Plutus, and Networking stacks while integrating with Cardano's on-chain governance mechanisms.

## Problem

Historically, Cardano operated with a single node implementation where features and changes were managed centrally. This centralized approach provided clear direction and ensured consistency, but it is no longer sufficient given the current ecosystem state.

Cardano now has multiple node implementations, each requiring coordination to maintain core compatibility across critical components: Ledger, Consensus, Plutus, and Networking. As well as with non-functional requirements, i.e. performance targets.

This evolution creates challenges:

1. **Critical Coordination**: Without a structured process, different node implementors may prioritize different CIPs, leading to inconsistent implementations.

2. **Panning**: Stakeholders lack visibility into which CIPs are planned for implementation, making it difficult for planning and budgeting.

3. **Hard Fork Planning**: Hard forks require careful coordination and packaging of multiple changes. Without a clear shortlist, planning and executing hard forks with multi-implementations will be impossible.

The absence of a formal shortlist process means that critical decisions are made centrally, inconsistently, or reactively, rather than through a transparent, community-driven process that considers all stakeholders.

## Goals

1. **Ensure Implementation Alignment**: Coordinate implementation priorities across all Cardano node implementations to maintain core compatibility in Ledger, Consensus, Plutus, and Networking components. This is critical to prevent ecosystem fragmentation.

2. **Enable Transparency**: Provide an open, transparent process where any Cardano stakeholder can propose CIPs for shortlisting and track their progress through implementation. The process must be accessible and understandable to all stakeholders.

3. **Maintain Quality Standards**: Ensure that shortlisted CIPs are properly evaluated, wanted, needed, documented. This includes assessing hard fork requirements, ledger era needs, dependencies, and impact areas.

### Non-Goals

- **Gatekeeping**: The process should not gatekeep which CIPs can be proposed. Any approved CIP can be proposed for shortlisting.

- **Implementation Mandates**: The shortlist does not mandate implementation—it coordinates priorities. Individual implementors retain autonomy in their implementation decisions.

- **Scope Mandates**: The shortlist does not extend beyond the scope of core categories and non-functional requirements.

- **CIP Creation**: The process does not create or approve CIPs themselves. CIPs must be approved through the existing CIP process before being eligible for shortlisting.

- **Technical Design**: The process does not design solutions—it coordinates the implementation of already-approved CIPs.

- **Scoping hardforks**: The process does not organise hard forks, rather it allows implementors to coordinate on a roadmap of implementation, this can be used to inform hard fork planning.

### Requirements

- **Open Process**: The process must be open to all stakeholders, with clear documentation and accessible contribution mechanisms.

- **Format Compliance**: Shortlist entries must follow a standardized format to ensure consistency and enable automated validation.

- **Maintainer Independence**: Maintainers should facilitate the process but not gatekeep content decisions. The community decides what gets shortlisted.

- **Traceability**: All shortlist decisions and changes must be traceable through version control and documented discussions.

## Open Questions

1. **Governance Integration**: What role can Cardano's on-chain government play?

2. **Priority Ranking**: How should CIPs be ranked and prioritized? What criteria should be used (technical readiness, community demand, dependencies, governance support)? How should conflicts between different priority criteria be resolved?

3. **Dependency Management**: How should dependencies between CIPs be managed? What happens if a dependent CIP is delayed or cancelled? How should circular dependencies be handled?

4. **Multi-Implementation Coordination**: How should the process handle situations where different node implementations have different capabilities or constraints? Should the shortlist be implementation-agnostic, or should it track implementation-specific requirements?

5. **Removal Process**: Under what conditions should a CIP be removed from the shortlist? Who has authority to remove CIPs, and what is the process for doing so?

6. **Quality Gates**: What are the minimum requirements for a CIP to be added to the shortlist? Should there be technical readiness criteria beyond CIP approval?

7. **Maintainer Selection**: How should maintainers be selected, and what are their specific responsibilities? How should maintainer conflicts of interest be handled?

8. **Metrics and Evaluation**: How should the success of the shortlist process be measured? What metrics indicate that the process is achieving its goals?
