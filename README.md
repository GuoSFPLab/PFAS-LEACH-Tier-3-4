# PFAS-LEACH-Tier-3-4

The PFAS-LEACH-Tier-3-4 repository provides an Excel-based tool implementing the Tier 3 and Tier 4 models—**PFAS-LEACH-Analytical** and **PFAS-LEACH-DAF**—of the PFAS-LEACH platform. Developed by Prof. Bo Guo's team at the University of Arizona, PFAS-LEACH is a comprehensive decision support system designed to predict per- and polyfluoroalkyl substances (PFAS) leaching in source zones.

## Features

- **PFAS-LEACH-Analytical (Tier 3):** The PFAS-LEACH-Analytical model allows one to compute, over time, the spatial profiles of PFAS concentration in the vadose zone, mass discharge rates to groundwater, and the groundwater PFAS concentration in a receptor well at the edge of the contaminated site. Additionally, given an acceptable PFAS concentration in groundwater, PFAS-LEACH-Analytical derives a site-specific soil screening level for a specific PFAS.
- **PFAS-LEACH-DAF (Tier 4):** PFAS-LEACH-DAF is a revision to the widely used dilution attenuation factor (DAF) approach in the USEPA SSL framework \citep{usepa1996soil} for determining SSLs for PFAS \citep{brusseau2023revising}. The revised PFAS-specific DAF approach considers the adsorption of PFAS at the air--water interfaces when converting the porewater concentration to a soil concentration. PFAS-LEACH-DAF is a simple algebraic model to compute site-specific SSLs for PFAS. It does not represent any transport processes in the vadose zone (e.g., attenuation) and does not generate any space- or time-dependent results.

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

For questions or support, please contact the development team at [boguo@arizona.edu](mailto:boguo@arizona.edu).
