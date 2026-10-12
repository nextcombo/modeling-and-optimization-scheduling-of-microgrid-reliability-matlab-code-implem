# Modeling and Optimization Scheduling of Microgrid Reliability (Matlab Code Implementation)

This article only displays a portion of the code:
clear format long\n% 1 Wind speed modeling (Weibull distribution) based on the found data\n% 1.1 Read historical data\nstd_v_history=  1.1;\nmean_v_history=  1;\n\n\n% 1.2 Parameter Estimation (Large-Sample Approximation)\nk=(std_v_history/mean_v_history)^-1.086;\nc=0;\nif (k>0.8 && k<1)\n    c = 1.03*k*mean_v_history;\nelseif k>1\n    c = 1.07*mean_v_history;\nelse\n    c = -1;\nend\n\n\n% 1.3 Wind Speed Model (Parameters from 1.2)\n% pdf(v,c,k) and cdf(v,c,k)\n% Current wind speed\nv = c * (-log(rand))^(1/k);\n\n\n% 1.4 Power model (wind speed from 1.3)\n% w(v)\n% The output of each normal operating fan\nP_1 = w(v);\n\n\n% 1.5 Unit Start-Stop Modeling\nN = 1000; % Assumed number of fans\n% For individual wind turbines:\n% Repair rate\nmiu = 1; \n%Failure rate\nlamda = 1;  \n%Normal probability\np0 = miu/(miu+lamda);  \n% Fault Probability\np1 = lamda/(miu+lamda);\n% The normal number of fans to be operated\nn0 = binornd(N , p0); \n% Total fan output power\nP_N = n0 * P_1; \n\n\n% 1.6 (Comprehensive) System State Acquisition and Analysis\n% Traditional unit output\nW_M = 0;\n% Total load\nL_sigma = 100;\n% Evaluation Index EDNS\nEDNS = L_sigma - W_M - P_N;\n\n\n\n\n    \n\n\n% 2. Examples\n% 2.1 Wind Speed Generation\n%\n\n\n\n\n\n\n  

## Images

![Modeling and optimizing dispatch for microgrid reliability (Matlab code implementation)](cover.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
