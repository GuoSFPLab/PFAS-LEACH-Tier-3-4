# PFAS-LEACH-Tier-3-4

This repository provides **two independent implementations of the PFAS-LEACH graphical user interface (GUI)** for evaluating PFAS soil-to-groundwater leaching and deriving site-specific soil screening levels (SSLs):

- **[Excel-based GUI](Excel-based%20GUI/):** A macro-enabled Microsoft Excel workbook.
- **[Python-based GUI](Python-based%20GUI/):** A local Python application distributed as desktop applications for macOS (Apple Silicon) and Windows (x64).

Both GUIs implement the same analytical framework: PFAS-LEACH-Analytical (Tier 3), PFAS-LEACH-DAF (Tier 4), and the standard USEPA dilution–attenuation factor (DAF) calculation for comparison. Both support parameter specification, deterministic simulation, sensitivity analysis, Monte Carlo uncertainty analysis, visualization, and export of results.

PFAS-LEACH is a decision-support platform for predicting PFAS leaching in source zones, with four model tiers of decreasing complexity. This repository provides the Tier 3 and Tier 4 GUIs. The more detailed PFAS-LEACH-COMP (Tier 1) model represents flow, transport, and transformation in three dimensions ([Guo et al., 2020](https://doi.org/10.1029/2019WR026667); [Zeng & Guo, 2021](https://doi.org/10.1016/j.advwatres.2021.104015)). [PFAS-LEACH-Numerical-1D](https://github.com/GuoSFPLab/PFAS-LEACH-Numerical-1D) (Tier 2), implemented within a modified open-source version of HYDRUS-1D, focuses on one-dimensional vertical leaching ([Zeng et al., 2021](https://doi.org/10.1016/j.jhydrol.2021.127172)). Tiers 1 and 2 are not included in the GUIs distributed here.

## Getting Started

### Excel-based GUI

1. **Download Excel-based GUI v1.1:**
   - [Excel_Tool_for_PFAS-LEACH_Tier_3_4_v1.1.xlsm](Excel-based%20GUI/Excel_Tool_for_PFAS-LEACH_Tier_3_4_v1.1.xlsm?raw=true)
   - Download the workbook and open it in desktop Microsoft Excel from a local drive. The Excel-based GUI may not display properly when the file is opened from an online drive.
2. **Enable Macros:**
   - Ensure macros are enabled in Excel to utilize the tool's full functionality.
3. **Refer to the User Guide for detailed instructions:**
   - [User_Guide_PFAS-LEACH_Tiers_3_4_v1.1.pdf](User_Guide_PFAS-LEACH_Tiers_3_4_v1.1.pdf)

### Python-based GUI

The Python-based GUI runs locally in its own desktop window and requires no Excel, macros, or separate Python installation. Download Python-based GUI v1.1 for your operating system below. These downloads contain packaged applications; Python source code is not included in this repository.

**macOS (Apple Silicon)**

1. **Download:** [PFAS-LEACH-macOS-arm64.zip](Python-based%20GUI/PFAS-LEACH-macOS-arm64.zip?raw=true)
2. **Requirements:** Apple Silicon Mac (M1 or newer), macOS 12 or later.
3. **First launch:** Extract the ZIP and try opening `PFAS-LEACH.app` once. This application is not yet notarized by Apple. If macOS blocks it with a warning about an unverified developer or an app that Apple cannot check:
   - Go to **System Settings → Privacy & Security**.
   - Scroll to **Security**, find the message about PFAS-LEACH, and click **Open Anyway**.
   - Authenticate if prompted and confirm **Open**.

   macOS saves an exception, so subsequent launches should work normally. See [Apple’s instructions](https://support.apple.com/en-us/102445).

4. **If macOS reports that the app is “damaged”:** Download the latest macOS ZIP again and extract a fresh copy using the built-in macOS Archive Utility (double-click the ZIP in Finder). Earlier packages contained `._` metadata files that some extraction methods left inside the app, causing its code-signature check to fail. The current package excludes these files. If the warning persists with a fresh copy, contact the development team with the exact message and your macOS version.

**Windows (x64)**

1. **Download:** [PFAS-LEACH-windows-x64.zip](Python-based%20GUI/PFAS-LEACH-windows-x64.zip?raw=true)
2. **Requirements:** Windows x64, Microsoft Edge WebView2 Runtime, and Microsoft .NET Framework 4.8.
3. **First launch:** Extract the entire ZIP to a writable folder (keep the `_internal` folder beside `PFAS-LEACH.exe`), then open `PFAS-LEACH.exe`. Windows SmartScreen may warn because the app is not signed; choose **More info**, then **Run anyway**.

Refer to the bundled User Guide (click any blue (i) icon or the (?) button in the app).

## Repository Layout

```text
Excel-based GUI/
  Excel_Tool_for_PFAS-LEACH_Tier_3_4_v1.1.xlsm
  Excel_Tool_for_PFAS-LEACH_Tier_3_4_v1.0.xlsm
Python-based GUI/
  PFAS-LEACH-macOS-arm64.zip
  PFAS-LEACH-windows-x64.zip
User_Guide_PFAS-LEACH_Tiers_3_4_v1.1.pdf
User_Guide_PFAS-LEACH_Tiers_3_4_v1.0.pdf
README.md
LICENSE
```

The GUI user guides apply to both the Excel-based and Python-based tools. Version numbers identify software releases within each implementation, such as **Excel-based GUI v1.1** and **Python-based GUI v1.1**. The v1.0 Excel workbook and User Guide are retained for reference; use the v1.1 release of either GUI for current analyses.

## Features

- **PFAS-LEACH-Analytical (Tier 3):** Analytical solutions represent one-dimensional vadose-zone transport by advection and dispersion, with equilibrium air–water interfacial adsorption and either equilibrium or rate-limited solid-phase sorption ([Guo et al., 2022](https://doi.org/10.1016/j.advwatres.2021.104102)). These solutions are coupled to a groundwater dilution factor model ([Smith et al., 2024](https://doi.org/10.1016/j.watres.2024.121236)). Outputs include time-dependent vadose-zone concentration profiles, mass discharge rates to groundwater, receptor-well concentrations, and site-specific SSLs for a user-specified acceptable groundwater PFAS concentration. Source conditions can include an initial soil concentration profile and optional finite-duration surface mass loading.
- **PFAS-LEACH-DAF (Tier 4):** A PFAS-specific revision of the USEPA DAF approach that includes air–water interfacial adsorption when converting porewater concentrations to soil concentrations ([Brusseau & Guo, 2023](https://doi.org/10.1016/j.hazl.2023.100077)). It derives site-specific SSLs from equilibrium partitioning and groundwater dilution, without explicitly simulating vadose-zone transport or attenuation. It does not generate space- or time-dependent results.
- **Standard USEPA DAF comparison:** Both GUIs also calculate SSLs using the migration-to-groundwater approach in the [USEPA Soil Screening Guidance (1996)](https://www.epa.gov/superfund/superfund-soil-screening-guidance). This calculation omits air–water interfacial adsorption and explicit vadose-zone transport attenuation. These are calculated screening estimates using the specified inputs, not screening values published by USEPA.

### Analysis modules shared by both GUIs

| Module | Analysis | Purpose |
| --- | --- | --- |
| Module 0 | Deterministic | Simulate PFAS leaching and derive SSLs using a single parameter set. |
| Module 1 | Sensitivity | Compare baseline results with user-defined left- and right-bound parameter scenarios to examine individual or combined input changes. |
| Module 2 | Monte Carlo uncertainty | Propagate prescribed input distributions and parameter dependencies to obtain ensembles of predictions and summary statistics. |

The modules can be selected independently and do not need to be run sequentially. Built-in reference data cover 12 soil textural classes and 45 PFAS. Reference values and parameter-estimation functions support input specification when measurements are unavailable; their applicability to the site should be evaluated, and site-specific measurements or estimates should be used where appropriate.

### Differences between the GUIs

| Function | Excel-based GUI | Python-based GUI |
| --- | --- | --- |
| Interface | Workbook with color-coded input cells and buttons | Expandable input sections within a local application |
| Updating estimated parameters | Reapply the estimation function after changing its inputs | Derived values update automatically unless manually overridden |
| Revising a completed analysis | Update estimates and rerun the analysis after changing inputs | Changes to relevant inputs mark results as outdated and prompt a rerun |
| Saving an assessment | Save a separate workbook containing inputs, settings, and results | Save and reload cases containing inputs and analysis settings |
| Rosetta soil hydraulic estimates | Obtain estimates externally and enter them into the workbook | Estimate parameters directly from soil texture and, when available, bulk density using built-in Rosetta access |

### Model assumptions and interpretation

Tier 3 assumes one-dimensional transport through a homogeneous, uniformly unsaturated vadose zone, steady-state water flow, and linear adsorption. Tier 4 derives SSLs directly from equilibrium partitioning and does not simulate vadose-zone transport. Both tiers use simplified groundwater dilution and omit precursor transformation. Monte Carlo results are conditional on the prescribed input distributions, dependencies, and model assumptions. The framework supports screening-type assessments and can inform further site investigation and more detailed modeling.

## Version History

### Excel-based GUI

- **Official releases**
   - November 5th, 2026: Updated v1.1.
      1) Improved the numerical stability and accuracy of the kinetic sorption solver in Modules 0 and 1.
      2) Corrected the coupling between water content and soil hydraulic parameters in Module 2 to improve Monte Carlo calculations.
   - September 14th, 2026: Updated v1.1.
      1) Accelerated the Kinetic Solution solver to improve computational efficiency.
   - August 20th, 2026: Updated v1.1
      1) Implemented a variable depth grid with 1-cm resolution in the upper 10 m and 10-cm resolution below 10 m to improve computational efficiency for thick vadose zones.
      2) Revised the attenuation factor (AF) calculations to account for both the initial concentration profile and the finite-duration surface mass-loading boundary condition during the active loading period.
      3) Implemented an adaptive fine-grid scheme with sub-centimeter resolution to improve numerical accuracy for small-scale domains and laboratory sand-column experiments.
  - July 1st, 2026: Release of v1.1.
      1) Added an optional finite-duration surface mass loading boundary condition for PFAS-LEACH-Analytical to simulate continuous PFAS release from surface sources.
      2) Updated the Monte Carlo simulation functionality in Module 2.
  - October 20th, 2025: Updated v1.0
      1) Added a warning in the Output Screen when dt is too big.
  - October 18th, 2025: Updated v1.0
      1) Updated the database of PFAS properties for Module 2. 
      2) Updated the user guide to remind users that the output dt for the time series needs to be sufficiently fine to capture the time evolution of mass discharge rates. 
      3) Updated the user guide to remind users that they can use the SF estimated from the porewater concentration data for one representative PFAS and use it for other PFASs at the same site.
  - October 1st, 2025: Release of v1.0. 
      1) Added Module 2 that allows for Monte Carlo-type uncertainty analysis.
      2) Added a parameter visualization toolkit to visualize the parameter distributions in Module 2.
      3) Revised the user interface for Modules 0, 1, and 2, especially the table for inputing lysimeter porewater data. 
      4) Revised the user guide to cover all three modules and their example applications. 

- **Beta version** - Initial Release for testing
  - July 30th, 2025: Added two new features. 
      1) Allow for using lysimeter porewater concentration to estimate air-water interfacial area.
      2) Output spatial concentration profiles. 
  - Feb 28th, 2025: Implemented core functionalities of PFAS-LEACH-Analytical and PFAS-LEACH-DAF models.

### Python-based GUI

- **Official releases**
  - November 25th, 2026: Repackaged the macOS v1.1 download to exclude extraneous `._` metadata files that could cause code-signature verification failures after extraction. Application files, symbolic links, and existing signatures are unchanged.
  - November 2026: Initial release (v1.1). Independent Python implementation of the Tier 3 and Tier 4 analytical framework, distributed as desktop applications for macOS (Apple Silicon) and Windows (x64). Runs locally with no Excel, macros, or separate Python installation. [PFAS-LEACH-Numerical-1D](https://github.com/GuoSFPLab/PFAS-LEACH-Numerical-1D) (Tier 2) is not included in this release.

## Acknowledgements

The PFAS-LEACH GUI framework is developed at the University of Arizona under the direction of Prof. Bo Guo. We acknowledge funding support from the Environmental Security Technology Certification Program (ESTCP Project ER21-5041).

## License

This project is licensed under the [CC BY-ND 4.0 License](LICENSE).

## Contact

For questions, please contact the development team at boguo@arizona.edu.
