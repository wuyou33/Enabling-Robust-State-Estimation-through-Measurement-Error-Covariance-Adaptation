# Enabling Robust State Estimation through Measurement Error Covariance Adaptation


## Overview

This repository contains the software release for "Enabling Robust State Estimation through Measurement Error Covariance Adaptation". The objective of the software release is described through the associated abstract.
<br/>
<br/>


> Accurate platform localization is an integral component of most robotic systems. As these robotic systems become more ubiquitous, it is necessary to develop robust state estimation algorithms that are able to withstand novel and non-cooperative environments. When dealing with novel and non-cooperative environments, little is known a priori about the measurement error uncertainty, thus, there is a requirement that the uncertainty models of the localization algorithm be adaptive. Within this paper, we propose one such technique that enables robust state estimation through the iterative adaptation of the measurement uncertainty model. The adaptation of the measurement uncertainty model is granted through non-parametric clustering of the residuals, which enables the characterization of the measurement uncertainty via a Gaussian mixture model. The provided Gaussian mixture model can be utilized within any non-linear least squares optimization algorithm by approximately characterizing each observation with the sufficient statistics of the assigned cluster (i.e., each observation's uncertainty model is updated based upon the assignment provided by the non-parametric clustering algorithm). The proposed algorithm is verified on several collected GNSS data sets, where it is shown that the proposed technique exhibits some advantages other robust estimation techniques when confronted with degraded data quality.

<br/>
<br/>

This software benefits from several open-source software packages.
* [*Georgia Tech Smoothing And Mapping (GTSAM)*](https://bitbucket.org/gtborg/gtsam/src/develop/) -- contains factor graph based state estimation algorithms
	* GTSAM was updated for GNSS signal processing within
	    *  [*PPP-BayesTree*](https://github.com/wvu-navLab/PPP-BayesTree) -- contains pseudorange and carrier-phase factors
	    *  [*RobustGNSS*](https://github.com/wvu-navLab/RobustGNSS) -- contains robust GNSS models
* [*GPS Toolkit (GPSTk)*](http://www.gpstk.org/bin/view/Documentation/WebHome) -- contains GNSS observation modeling tools
* [*libcluster*](https://github.com/dsteinberg/libcluster) -- contains variatinal clustering algorithms


<br/>
<br/>
<br/>

<!--
If you utilze this software for an academic purpose, please consider using the following citation:
-->
<!--
```
@article{ watson2019enabling,
        title={Enabling Robust State Estimation through Measurement Error Covariance Adaptation},
        author={Watson, Ryan M and Gross, Jason N and Taylor, Clark N and Leishman, Robert C},
        journal={arXiv preprint},
        year={2019}
       }
```
-->

<br/>
<br/>

## How to Install


### 1) Requirements/Recommendations

#### Required
* Boost -->  ```` sudo apt-get install libboost-all-dev ````
* CMake -->  ```` sudo apt-get install cmake ````
* OpenMP --> ```` sudo apt install libomp-dev ````


### 2) Clone repository to local machine  
````bash

git clone https://github.com/wvu-navLab/Enabling-Robust-State-Estimation-through-Measurement-Error-Covariance-Adaptation.git

````

### 3) Build

````bash

cd Enabling-Robust-State-Estimation-through-Measurement-Error-Covariance-Adaptation
./build.sh

````

### 4) Test
````bash
cd examples
chmod +x run_all.sh
./run_all.sh
````

This will write all of the generated results to the *test* directory (*../test*). To duplicate the plots generated within the paper run the following command. (Note: this assumes that you have a matlab alias set. See this [link](https://www.mathworks.com/matlabcentral/answers/98220-how-do-i-create-a-shortcut-or-link-to-matlab)  for instructions. ).

````bash
chmod +x plot_all.sh
./plot_all.sh
````

This will write all of the generated figures to the *test/plots* directory.
