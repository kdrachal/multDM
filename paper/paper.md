---
title: 'multDM: An R package for multivariate version of the Diebold-Mariano test'
tags:
  - R
  - multivariate Diebold-Mariano test
  - forecast comparison 
  - Equal Predictive Accuracy
authors:
  - name: Krzysztof Drachal
    orcid: 0000-0001-5297-6695
    affiliation: 1
affiliations:
 - name: Faculty of Economic Sciences, University of Warsaw
   index: 1
date: 27 March 2020
bibliography: paper.bib
---

# Summary

It is quite often in econometric analysis that more than two time-series models
are considered. If these models are used in forecasting, then it becomes 
interesting to investigate the predictive ability between those models. In case 
of two forecasts from two competing models the Diebold-Mariano test is a very
popular tool [@dmtest]. Mariano and Preve proposed a multivariate version of 
this test for non-nested forecasting models [@mdmtest]. 

In particular, this test relies on Equal Predictive Ability (EPA). In short, 
suppose that initially the researcher is given some set of forecasts coming 
from several competing models. Then, a certain loss function has to be specified.
For example, very common one is the squared loss function. The EPA hypothesis
states that the expected values of the loss function evaluated over forecast 
errors from competing models are equal to each other [@mdmtest].

Starting from the initial set of forecasts coming from competing models, the EPA 
can be statistically tested. If the EPA holds, the procedure stops. Otherwise, 
under a certain criterion, one forecast can be eliminated. Then, this procedure 
can be recursively repeated [@mdmtest]. Similar methodology was proposed by 
Hansen et al. through the Model Confidence Set (MSC) [@mcs]. MCS procedure was 
implemented in R by Catania and Bernardi [@mcsR].

``multDM`` package contains the function ``DM.test`` which computes the original
Diebold-Mariano test for two forecasts. ``MDM.test`` function computes the 
multivariate version of this test, i.e., tests if EPA holds for two or more 
forecasts. ``MDM.selection`` function performs the procedure of selecting the
models with outstanding predictive ability based on the multivariate 
Diebold-Mariano test. For the given forecasts several loss functions, 
consistent with the test procedure, can be computed [@loss1; @loss2; @loss3; 
@ase]. For example, squared errors, absolute errors, squared proportional errors, 
absolute scaled errors and the function based on the exponential loss. The 
package contains also the function ``loss``, which computes various loss 
functions. Additionally, the package contains ``TB_MA`` function, which
allows to check the necessary lag for VMA process with the Tiao-Box procedure
[@tb]. Following Mariano and Preve [@mdmtest], such a verification should be 
done over (stationary) loss differential, and used in the specification of 
``MDM.test`` and ``MDM.selection``. Additionally, the function ``TB_AR_test``
performs the Tiao-Box test for autocorrelation.

The package contains ``oilforecasts`` data set. It consists of forecasts of 
log-differences of real average world oil price forecasted by several 
econometric models [@models]. This can serve as an illustration of an 
application of the test. The source code for ``multDM`` has been archived to 
CRAN [@cran] and GitHub [@github]. 

# Acknowledgements

Research funded by the Polish National Science Centre grant under the contract
number DEC-2015/19/N/HS4/00205.

# References
