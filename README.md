# ARGA
Adaptive Robust Genetic Algorithm

Adaptive Robust Genetic Algorithm (ARGA) optimizes zero-one simulation problems by incorporating input uncertainty. In ARGA, a surviving population of solutions evolves as more information about the high-dimensional problem affected by stochasticity becomes available. A ranking and selection operation in each iteration is enhanced with a debiasing mechanism of fitness values using fast iterated bootstraps and control variates. Debiasing reduces the model risk from input uncertainty bias, obtaining a more accurate ranking of the current surviving solutions. Given the double loop of function evaluations, we adaptively increase budget only if the current population’s proximity to optimality signals the need for a smaller standard error. In that case, we allocate additional replications to the input model of a current surviving solution that is most responsible for risk. The empirical results with a fixed optimization budget demonstrate that ARGA obtains significantly better solutions in a feature selection problem on various datasets.

Paper: *Vahdat, K. and Shashaani, S., Adaptive Ranking and Selection Based Genetic Algorithms for Data-driven Problems, In Proceedings of the 2023 Winter Simulation Conference, edited by C.G. Corlu, S.R. Hunter, H. Lam, B.S. Onggo, J. Shortle, and B. Biller. Piscataway, New Jersey: IEEE Inc.
DOI: 10.1109/WSC60868.2023.10408610 


# Script

## Overview

The `main()` function is the entry point for executing the RSGA (Ranking and Selection Genetic Algorithm) analysis on simulated datasets. This function automates the process of loading required packages, generating datasets, and running the RSGA algorithm on each dataset.

## Usage

To use the `main()` function, simply execute it in an R environment. The function will perform the following steps:

1. Load Required Packages: It loads necessary R packages such as caret, dplyr, GA, doParallel, and extraDistr. If any of these packages are not installed, the function will install them.

2. Set Up Parallel Processing: It sets up parallel processing using the `doParallel` package to speed up computations.

3. Define Experiment Parameters: It defines parameters such as the number of macro-replications (N), the number of post-processing iterations (P), the maximum number of micro-replications (B), and the experiment name (Exp_Name).

4. Generate Datasets: It generates four simulated datasets using the `generate_datasets()` function. Two datasets have 15 predictors each, and the other two datasets have 30 predictors each. Two datasets have correlation among predictors (Corr = TRUE), while the other two do not have correlation (Corr = FALSE).

5. Run RSGA Algorithm: It runs the RSGA algorithm on each dataset using the `run_rsga()` function. This involves selecting a subset of predictors using the genetic algorithm and evaluating the performance of the selected predictors.

6. Output Results: It saves the results of the RSGA analysis to CSV files, including the selected predictors and evaluation metrics.

## File Structure

The function assumes that the datasets will be saved in the current directory (please adjust the directories as needed). The generated datasets will be named "Dataset_1.csv", "Dataset_2.csv", etc., with "Corr" appended to the filenames for datasets with correlated predictors.

## Example

```R
# Execute the main function
main()

