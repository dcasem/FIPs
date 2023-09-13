---
fip: "0000"
title: Phasing Out Fil+ and Restoring Deal Quality Multiplier to 1x
author: "@The-Wayvy, @Fatman13, @ArthurWang1255, @flyworker, @stuberman, @Eliovp, @dcasem"
discussions-to: https://github.com/filecoin-project/FIPs/discussions/774
status: Draft
type: Technical
category: Core
created: 2023-08-03
---

## Summary

This proposal eliminates the 10X multiplier associated with Fil+ deals, effectively restoring the deal multiplier to its raw byte value.

## Authors

@Fatman13, @ArthurWang1255, @stuberman, @Eliovp, @dcasem, @The-Wayvy 

## Motivation

The Fil+ program's current implementation has created complexities and challenges that hinder the growth trajectory of the Filecoin network. By phasing out the Fil+ multiplier, this proposal seeks to restore the integrity of Filecoin blockchain and alleviate issues related to consensus overload, complexity, pledge availability, poor UX, loss of privacy/censorship resistance, and other problems outlined in the initial discussion[LINK].

## Specification

### Elimination of the 10X Multiplier


1. ***Removal of Verifreg Actor***: The Verifreg actor will be removed following the update. 
2. **Existing Deals**: For sectors with existing Fil+ deals (DC sectors), the current Quality Adjusted Power (QAP) will remain until these deals expire. Technical solutions may need to be devised to ensure a smooth transition.
3. **Sector Extension**: Upon sector extension, the 10x multiplier will no longer be applicable after the upgrade.

### Technical Changes

The following technical changes must be implemented to facilitate this proposal:

- **Remove Verireg Actor**: The verifreg actor will be removed following the update.This change will stop the issuance of new DataCap, while existing DataCap and Quality Adjusted Power (QAP) will remain untouched. 
- **Block New Datacap Requests**: Prevent any new requests for Datacap allocations within the protocol.
- **Transition Handling for Existing Deals**: Implement mechanisms to handle the transition for existing DC sectors, ensuring that they continue with the current QAP until expiration.

## Rationale

This proposal aligns with Filecoin's mission to provide useful storage and maintains the network's core values of decentralization, objectivity, and permissionlessness. It aims to reduce complexity and friction in the ecosystem, encourage the onboarding of real data, and foster a healthier growth environment for the Filecoin network.

## Impact and Migration

- **Storage Providers (SPs)**: SPs need to adjust to the new multiplier rules and consider their strategies for attracting non-Fil+ deals.
- **Data Clients**: The transition may affect existing clients using Fil+. New mechanisms that are not embedded in Filecoin’s core protocol to promote real data storage can be developed.
- **Existing Deals**: Existing Fil+ deals will remain unaffected until their expiration.The extra pledge will be returned once the sector is terminated or expires. 
- **Network Stability**: Care must be taken to ensure network stability during the transition, especially when handling existing deals.

## Security Considerations

This FIP does not introduce new security concerns. However, it is critical to ensure that the transition is handled securely, particularly when dealing with existing sectors.

## Afterwards
Fil+ team and many more customized deal markets will be developed on L2 of Filecoin in either permissioned or permissionless manners in an open and fair market competition. 
By way of example. If the community consensus determined the end of multipliers in NFV21 (proposed Nov 2023) upgrade,  then sectors with multipliers would conclude at the end of May 2025.



## References

* [Initial Discussion](https://github.com/filecoin-project/FIPs/discussions/774)
* [FIP-003](link_to_FIP-003)

Why pick option1 over option2:<br> 
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6656805<br>
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6664701<br>
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6677630<br>

Why 10x for all, a soft landing, is not ideal: <br>
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6677066<br>
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6654608<br>
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6655524<br>

Why no more multiplier should be applied in the Filecoin core protocol: <br> 
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6686571 <br>
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6686564 <br>
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6664701 <br>
-https://github.com/filecoin-project/FIPs/discussions/774#discussioncomment-6644045 <br>


## Copyright

This work is licensed under the Apache License, Version 2.0.

---

This FIP provides a detailed and structured plan to phase out Fil+ by changing the deal quality multiplier, adhering to the chosen option and the principles outlined in the initial discussion. Implementing this proposal will need careful planning and consideration to ensure a smooth transition and alignment with Filecoin's long-term objectives.