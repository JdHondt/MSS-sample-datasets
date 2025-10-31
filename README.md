# Time Series Datasets for Multivariate Similarity Search

This repository contains sample datasets for multivariate similarity search on time series data, created as part of the **Correlation Detective** project at TU Eindhoven.

## About

These datasets were developed to support research in multivariate time series analysis and similarity search algorithms. For more detailed information about the datasets and their applications, please refer to our publication:

**Publication:** [d'Hondt, J.E., Minartz, K., Papapetrou, O. "Efficient detection of multivariate correlations with different correlation measures"](https://link.springer.com/article/10.1007/s00778-023-00815-y) _The VLDB Journal_, 2023.

**Project Website:** [https://correlationdetective.com](https://correlationdetective.com)

## Datasets

This repository contains six datasets:

### 1. Stocks
- **Description:** Daily closing prices of 100 stocks (log-returns)
- **Period:** January 2, 2016 to December 31, 2020
- **Dimensions:** 100 time series
- **Length:** 1,309 observations per series
- **File:** `stocks.csv`

### 2. fMRI
- **Description:** Functional MRI data of a person watching a movie
- **Source:** [OpenNeuro dataset ds002837](https://openneuro.org/datasets/ds002837/versions/2.0.0)
- **Processing:** Mean-pooling with kernel size 8×10×8 from file `sub-1_task-500daysofsummer_bold_blur_censor`
- **Dimensions:** 237 time series
- **Length:** 5,470 observations per series
- **File:** `fmri.csv`

### 3. SLP (Sea Level Pressure)
- **Description:** Sea level pressure readings from 100 weather sensors
- **Source:** ISD weather dataset segment
- **Period:** January 1, 2016 to December 31, 2020
- **Dimensions:** 100 time series
- **Length:** 2,927 observations per series (daily averages)
- **File:** `weather_slp.csv`

### 4. TMP (Temperature)
- **Description:** Atmospheric temperature readings from 100 weather sensors
- **Source:** ISD weather dataset segment
- **Period:** January 1, 2016 to December 31, 2020
- **Dimensions:** 100 time series
- **Length:** 2,927 observations per series (daily averages)
- **File:** `weather_tmp.csv`

### 5. Crypto
- **Description:** 3-hour closing prices of 100 cryptocurrencies (log-returns)
- **Period:** April 14, 2021 to July 13, 2021
- **Dimensions:** 100 time series
- **Length:** 713 observations per series
- **File:** `crypto.csv`

### 6. Deep
- **Description:** Embeddings extracted from final layers of a convolutional neural network
- **Dimensions:** 100 time series
- **Length:** 96 observations per series
- **File:** `deep.csv`

## Data Format

All datasets are provided as CSV files with the following structure:
- **Rows:** Each row represents one time series
- **Columns:** The first column contains the time series index (0-based), and subsequent columns contain the values at each time point
- **Values:** Numerical values (floating-point)

### Example Structure

```csv
,0,1,2,3,4,...
0,value,value,value,value,value,...
1,value,value,value,value,value,...
2,value,value,value,value,value,...
```

## Usage

### Loading Data in Python

```python
import pandas as pd
import numpy as np

# Load a dataset
df = pd.read_csv('stocks.csv', index_col=0)

# Convert to numpy array
data = df.values

print(f"Dataset shape: {data.shape}")
print(f"Number of time series: {data.shape[0]}")
print(f"Length of each time series: {data.shape[1]}")
```

### Loading Data in R

```r
# Load a dataset
data <- read.csv('stocks.csv', row.names=1)

# Convert to matrix
data_matrix <- as.matrix(data)

print(paste("Number of time series:", nrow(data_matrix)))
print(paste("Length of each time series:", ncol(data_matrix)))
```

## Citation

If you use these datasets in your research, please cite our paper:

```bibtex
@article{dhondt2024cd,
    author={d'Hondt, Jens E.
    and Minartz, Koen
    and Papapetrou, Odysseas},
    title={Efficient detection of multivariate correlations with different correlation measures},
    journal={The VLDB Journal},
    year={2024},
    month={Mar},
    day={01},
    volume={33},
    number={2},
    pages={481-505},
    issn={0949-877X},
    doi={10.1007/s00778-023-00815-y},
    url={https://doi.org/10.1007/s00778-023-00815-y}
}
```

## License

Please refer to the original data sources for licensing information:
- **fMRI data:** Licensed under the terms of the OpenNeuro dataset ds002837
- **Weather data:** From the ISD (Integrated Surface Database)
- **Other datasets:** Please contact the authors for licensing details

## Contact

For questions or issues regarding these datasets, please contact:
- **Project Website:** [https://correlationdetective.com](https://correlationdetective.com)
- **Email:** [o.papapetrou@tue.nl](mailto:o.papapetrou@tue.nl)
- **Institution:** TU Eindhoven, Department of Mathematics and Computer Science

## Acknowledgments

This work was conducted at the Databases group at TU Eindhoven as part of the Correlation Detective project.
