# PFAS-LEACH-Tier-3-4

The PFAS-LEACH-Tier-3-4 repository provides an Excel-based tool that includes implementations of the Tiers 3 and 4 models (PFAS-LEACH-Analytical and PFAS-LEACH-DAF) of PFAS-LEACH. 

PFAS-LEACH is a comprehensive decision support platform for predicting PFAS leaching in source zones, developed by a team at the University of Arizona led by [Prof. Bo Guo](https://guolab.arizona.edu/). It is comprised of four tiers of models at different levels of model complexity. In addition to the simplified Tiers 3 and 4 models documented here, PFAS-LEACH also includes two more sophisticated models (Tiers 1 and 2). The Tier 1 model incorporates a comprehensive representation of flow, transport, and transformation processes in three dimensions (3D), referred to as PFAS-LEACH-COMP ([Guo et al., 2020](https://doi.org/10.1029/2019WR026667); [Zeng & Guo, 2021](
https://doi.org/10.1016/j.advwatres.2021.104015)). The Tier 2 model (PFAS-LEACH-HYDRUS) incorporates a set of simplifications to focus on one-dimensional leaching along the vertical direction ([Zeng et al., 2021](
https://doi.org/10.1016/j.jhydrol.2021.127172)) and is implemented within a modified opensource version of the widely used industry-standard software, HYDRUS-1D. The codes for Tiers 1 and 2 models are being finalized and we hope to release the beta version soon.

## Features

- **PFAS-LEACH-Analytical (Tier 3):** The core of PFAS-LEACH-Analytical is a set of analytical solutions that solve the partial differential equations for the leaching of PFAS in the vadose zone ([Guo et al., 2022](
https://doi.org/10.1016/j.advwatres.2021.104102)). The vadose-zone analytical solutions are also coupled to a simple groundwater dilution factor model ([Smith et al., 2024](
https://doi.org/10.1016/j.watres.2024.121236)), which allows for computing PFAS concentration in a receptor well and deriving site-specific soil screening levels (SSLs) for a given acceptable groundwater PFAS concentration. The PFAS-LEACH-Analytical model allows one to compute, over time, the spatial profiles of PFAS concentration in the vadose zone, mass discharge rates to groundwater, and the groundwater PFAS concentration in a receptor well at the edge of the contaminated site. Additionally, given an acceptable PFAS concentration in groundwater, PFAS-LEACH-Analytical derives a site-specific soil screening level for a specific PFAS.
- **PFAS-LEACH-DAF (Tier 4):** PFAS-LEACH-DAF is a revision to the widely used dilution attenuation factor (DAF) approach in the USEPA SSL framework ([USEPA, 1996](https://www.epa.gov/superfund/superfund-soil-screening-guidance)) for determining SSLs for PFAS ([Brusseau & Guo, 2023](
https://doi.org/10.1016/j.hazl.2023.100077)). The revised PFAS-specific DAF approach considers the adsorption of PFAS at the air--water interfaces when converting the porewater concentration to a soil concentration. PFAS-LEACH-DAF is a simple algebraic model to compute site-specific SSLs for PFAS. It does not represent any transport processes in the vadose zone (e.g., attenuation) and does not generate any space- or time-dependent results.

## Getting Started

1. **Download the Tool:**
   - [PFAS-LEACH-Tier-3-4 Excel Tool](https://github.com/GuoSFPLab/PFAS-LEACH-Tier-3-4/releases)
2. **Enable Macros:**
   - Ensure macros are enabled in Excel to utilize the tool's full functionality.
3. **User Guide:**
   - Refer to the [User Guide](https://github.com/GuoSFPLab/PFAS-LEACH-Tier-3-4/releases) for detailed instructions.

## Version History

- **Beta version** - Initial Release for testing
  - Implemented core functionalities of PFAS-LEACH-Analytical and PFAS-LEACH-DAF models.

## Acknowledgements

The development of PFAS-LEACH was supported by the Environmental Security Technology Certification Program (Project ER21-5041).

## License

This project is licensed under the [CC BY-ND 4.0 License](https://github.com/GuoSFPLab/PFAS-LEACH-Tier-3-4/blob/main/LICENSE).

## Contact

For questions, please contact the development team at boguo@arizona.edu.
