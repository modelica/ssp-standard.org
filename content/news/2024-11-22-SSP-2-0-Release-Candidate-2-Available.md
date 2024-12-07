---
title: 2nd Release Candidate for SSP 2.0 is ready for review
date: 2024-11-22
---

# 2nd Release Candidate for SSP 2.0 is ready for review

The second candidate for the major releases [SSP 2.0](https://github.com/modelica/ssp-standard/releases/tag/v2.0-rc.2) is ready for final review.

The MA internal approval period will last until December 18th.
In case of findings, please open an issue on https://github.com/modelica/ssp-standard.
If there are no blockers detected, the MA will release SSP 2.0 afterwards.

## Changes in 2.0.0

This major release of the SSP standard provides support for FMI 3.0, as well as other enhancements in response to new end-user requirements for architectural design, traceability, incremental development, and support of Modelica models as components.

SSP 2.0 is a major version release, however all SSP 1.0 conforming artifacts remain fully conforming to SSP 2.0.
SSP 2.0 conforming artifacts are only conforming to the SSP 1.0 standard if they use a 1.0 version number and only use features available in SSP 1.0.

The following changes were performed as part of the 2.0.0 major release:

* Support for FMI 3.0
  * Support for the new basic data types: Float32/64, and [U]Int8/16/32/64.
    The binary data type was already supported in SSP 1.0.
  * Support for the new scheduled execution implementation kind in the component implementation attribute.
  * Support for clocks as a new connector kind, and clocked variables/connectors.
  * Support for arrays in connectors and connections in the SSD, as well as in the SSV and SSB file formats.
  * Support for structural parameters with the new connector kind `structuralParameter`.
  * Support for the redesigned alias variable handling in FMI 3.0.
* Architectural design features
  * The component source attribute is now optional to support the usage of system structure descriptions for simulation architecture design without available component implementations.
  * New connector kinds `local`, and `constant` are added to the specification, to support more encompassing interface specifications for components, and further parameter propagation.
  * Support for optional inner view connector coordinates, in addition to the outer view connector coordinates.
     This feature enables more advanced graphical editing of SSP models.
* Traceability and meta-data features
  * Integration of the `MetaData` element developed as part of the SSP Traceability layered standard into the core standard, supporting the integration of arbitrary meta-data and digital signatures into the SSP file formats.
     
  * Support for mixed content in annotations, as in FMI 3.0 and the SSP Traceability layered standard.
* Support for Modelica
  * Support in the core standard for Modelica models as components
  * Support for the mapping of complex Modelica types in interfaces to binary connectors in SSP
* General clarifications and bug fixes
  * Fix missing type of Connector name attribute in https://github.com/modelica/ssp-standard/pull/4
  * Clarify type conversion handling in https://github.com/modelica/ssp-standard/pull/21
  * Clarify uniqueness of root SSDs in https://github.com/modelica/ssp-standard/pull/23
  * Clarify hierarchical parameter name resolution in https://github.com/modelica/ssp-standard/pull/27

For full release notes see the [SSP 2.0.0-rc.2 GitHub Release Page](https://github.com/modelica/ssp-standard/releases/tag/v2.0-rc.2).
