This repository provides all R code for

Isabelle Halbhuber (2023) A comparison of statistical methods to establish no effect.

Additionally it contains the R code for

Mair, MM, Kattwinkel, M, Jakoby, O and Hartig, F (2020) The MDD concept for establishing trust in non-significant results - a critical review. The code is from the GitHub repository 'https://github.com/TheoreticalEcology/Mair-et-al-2020' and you can find it in the directory "Mair-et-al/Mair-et-al-2020-master".

Moreover the repository contains the R code

from Magdalena Mair received from Florian Hartig and you can find it in the directory "Mair-et-al/Mair-NoEffectSimulations". 


Abstract

Various statistical methods are designed or used to establish ‘no effect’. The true absence of an effect is not necessarily confirmed by a non-significant (p-value > 0.05) result of a traditional null hypothesis significance test (NHST) due to various factors such as too small effect sizes, a lack of statistical power, the presence of natural variance or associated error rates. These error rates, known as Type I and Type II errors, can lead to incorrect conclusions about the presence or absence of an effect. The probability of making these incorrect conclusions varies among statistical methods, like the minimum detectable difference (MDD), Confidence Intervals (CI), Bayes factors (BF) or Equivalence test (EQUIV). These statistical approaches can be used to decide whether a non-significant result is a false negative or indicates the true absence of an effect, thereby ensuring the safety of human health and the environment. To prevent environmental damage, potentially toxic chemicals are regulated through legislation by policymakers and the expertise of scientists. Scientists identify potentially toxic chemicals and their potential harmful effects by above mentioned statistical approaches. However, the determination of the most appropriate statistical method remains an important decision in establishing guidelines for risk assessment. In this study, I compare the four statistical methods for their False Mistrust and False Trust Rates (FMR and FTR) to identify the least error-prone statistical method. These rates reflect the probabilities of making incorrect conclusions when applying these methods. To provide a comprehensive understanding of these methods, I explain the theory behind them including the concept of MDD, the construction of CIs, the Bayesian approach using BF, and the principles of EQUIV. I perform simulations based on the R script by Magdalena M. Mair (2020) and finally, I will look at the European Food Safety Authority's (EFSA) switch to the use of EQUIV and the consequences for practical application. My main results are that CIs and EQUIV are performing the same in identifying true effects if they are present and that the new EFSA guidelines with the use of EQUIV require more animal testing than in the past. In conclusion, I support the findings of Mair et al. (2020) in recommending the use of CIs for the interpretation of non-significant results.


The code for the two simulations:

The R script "FMR_FTR_simulation" is designed to perform hypothesis testing and trust analysis for different statistical methods, including Minimum Detectable Difference (MDD), Confidence Interval (CI), Equivalence tests (EQUIV), Bayes Factor Ratio (BFRatio), and random value testing. It evaluates the trust in the "no effect" hypothesis using various statistical methods.

The R script "sampleSize_simulation" is designed to perform hypothesis testing and trust analysis for MDD and EQUIV. It evaluates the trust in the "no effect" hypothesis using MDD and EQUIV for different data sets displaying different sample sizes. 


Key components of the scripts include:

Data Generation: The script generates data sets with different effect sizes and sample sizes using the 'CreateSampleDataset' function.
Simulation Settings: It defines a grid of simulation settings, including methods (MDD, CI, EQUIV, BFRatio, random_values), threshold values, and dataset indices.
Parallel Processing: The script utilizes parallel processing for efficient computation by creating a cluster with 5 nodes.
Hypothesis Testing: It performs hypothesis testing for each simulation setting, calculates p-values, and determines whether the effect is detected.
Trust Analysis: The script calculates trust values for different methods and threshold levels and stores the results.
Aggregate and Visualize: It aggregates the results and visualizes the trust in the "no effect" hypothesis for each method. The 'plotResult' function is used to create line graphs that display False Mistrust Rates (FMR) against False Trust Rates (FTR) or "No effect trusted" against "dataset".

Usage: To use the script, you can modify the parameters in the 'CreateSampleDataset' function and execute the subsequent simulations. You can also customize the visualization of trust results by calling the 'plotResult' function with different methods.

External function: The two scripts have the option to use the function 'MDD_function_Mair.R', which comes from an external GitHub repository. This function provides specific calculations needed in the context of this project.

The source code file and more details about 'MDD_function_Mair.R' can be found in the Git repository 'https://github.com/TheoreticalEcology/Mair-et-al-2020'.

Dependencies

The script relies on the 'BayesFactor' library for Bayes Factor Ratio calculations.
The R Version 2023.06.2+561 (2023.06.2+561) was used.

License

This script is available under the MIT License.
