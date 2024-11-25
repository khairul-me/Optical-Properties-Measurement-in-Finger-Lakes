# Optical Properties Measurement in Finger Lakes

## Overview
This repository contains research work on measuring optical properties of water in Cayuga and Canandaigua Lakes using hyperspectral ocean color radiometry. The project focuses on monitoring water quality and harmful algal blooms (HABs) through advanced remote sensing techniques.


## Physical Principles
![physics-diagram](https://github.com/user-attachments/assets/990bde33-84d3-41f0-a88a-42b532d20442)

### Remote Sensing Reflectance (Rrs)
Remote sensing reflectance (Rrs) is defined as:

```
Rrs = Water-leaving spectral radiance / Downwelling spectral plane irradiance
    = Lw(λ) / Ed(λ)
```

where:
- Lw(λ) is measured in µW/cm²/nm/sr
- Ed(λ) is measured in µW/cm²/nm

### Key Physical Concepts

1. **Radiometric Measurements**
   - Spatial Irradiance Air (±3%)
   - Irradiance Water (±3%)
   - Radiance Air (3°)
   - Radiance Water (8.5°)

2. **Light-Water Interaction**
   - Absorption
   - Scattering
   - Fluorescence
   - Surface reflection (including sun glint)

3. **Spectral Range**
   - Measurements across 136 channels
   - Wavelength range: 350-800 nm
   - Key indicators:
     - Chlorophyll-a signatures
     - Total Suspended Matter (TSM) signatures

## Equipment

### HyperOCR Sensors
- Sea-Bird hyperspectral ocean color radiometer (HOCR)
- Two radiometer configurations:
  1. 281 ∟-sky radiometer
  2. 243 water-sky-facing radiometer
- Power: External 12V supply
- Interface: SatView Software

## Methodology

### Data Collection
1. **Setup**
   - Station configuration via SatView Software
   - Physical parameter logging from nearest weather station
   - Monthly collection (June-September)
   - Locations: Nearshore and offshore sites

2. **Measurement Protocol**
   ```
   Baseline Corrected Data = Light Data - Average Dark Data
   where:
   - Light Data: measured in µW/cm²/nm
   - Dark Data: ~20% of total light data points
   ```

3. **Sun Glint Correction**
   - Applied surface reflectance factor: 0.028
   - Conditions: Wind speed < 5 mph
   - Sensor angle: 90° with 40° viewing direction from sun

### Data Analysis
1. **Preprocessing**
   - Dark data correction
   - Baseline calculation
   - Sun glint removal

2. **Analysis Methods**
   - Correlation matrix computation
   - Spectral signature comparison
   - Time series analysis

## Results

### Key Findings
1. Early Season Characteristics
   - Similar optical properties between lakes
   - Consistent patterns across sampling sites

2. Bloom Conditions
   - Distinct spectral signatures
   - Variable correlation patterns
   - Site-specific optical properties

3. Temporal Patterns
   - Progressive differentiation of properties
   - Seasonal variation in correlation strength

## Future Development

### Planned Enhancements
1. Integration of additional parameters
2. Extended temporal analysis
3. Correlation studies with measured chlorophyll-a

## Requirements
- Python 3.x
- Required packages:
  ```
  numpy
  pandas
  matplotlib
  seaborn
  scipy
  ```

## Installation
```bash
git clone https://github.com/yourusername/finger-lakes-optical-properties.git
cd finger-lakes-optical-properties
pip install -r requirements.txt
```

## Usage
```python
# Example code for data processing
from src.processing import calculate_rrs
from src.visualization import plot_spectral_signature

# Calculate Rrs
rrs_data = calculate_rrs(light_data, dark_data)

# Plot results
plot_spectral_signature(rrs_data)
```

## Contributing
We welcome contributions to this project. Please read our contributing guidelines and submit pull requests for any enhancements.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments
- Finger Lakes Institute Endowment
- NYS Water Resources Institute
- Cornell University Collaboration
- FLI summer research colleagues and staff

## Contact
For questions and collaborations, please contact:
[Your Contact Information]

## References
1. Mobley, C. D. (1999). Estimation of the Remote-Sensing Reflectance from Above-Surface Measurements. Applied Optics, 38(36), 7442-7455.
2. O'Reilly, J.E. and P.J. Werdell. (2019). Chlorophyll algorithms for ocean color sensors. Remote Sensing of Environment, 229(32-47).
3. Augusto-Silva et al. (2014). Analysis of MERIS reflectance algorithms for estimating chlorophyll-a concentration. Remote Sensing, 6(12), 11689-11707.
