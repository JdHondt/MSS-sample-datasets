- \textbf{Stocks:} Daily closing prices of 100 stocks over the period Jan. 2, 2016 to Dec. 31, 2020 (1309 observations). 

- \textbf{fMRI:} Functional MRI data of a person watching a movie. Original data from [OpenNeuro](https://openneuro.org/datasets/ds002837/versions/2.0.0). We used file ``sub-1\_task-500daysofsummer\_bold\_blur\_censor'', which includes recommended preprocessing for voxel-based analytics. We this by mean-pooling with a kernel of different size 8x10x8 resulting in 237 time series respectively, each with 5470 observations. 

- \item \textbf{SLP \& TMP:} Segment of the ISD weather dataset containing sea level pressure (\textbf{SLP}) and atmospheric temperature (\textbf{TMP}) readings from 100 sensors. We used daily averages between January 1, 2016 and December 31, 2020 (2927 readings per time series). 

- \item \textbf{Crypto:} 3-hour closing prices of 100 crypto-currencies with 713 observations each, covering April 14, 2021 to July 13, 2021.

- \item \textbf{Deep:} 100 time series of length 96, obtained by extracting embeddings from the final layers of a convolutional neural network.