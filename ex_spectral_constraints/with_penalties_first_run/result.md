| Optimization Result           |                  |
|-------------------------------|------------------|
| Number of residual evaluation | 6                |
| Number of variables           | 5                |
| Number of datapoints          | 25552            |
| Degrees of freedom            | 25547            |
| Chi Square                    | 6.18e+01         |
| Reduced Chi Square            | 2.42e-03         |
| Root Mean Square Error (RMSE) | 4.92e-02         |
| RMSE additional penalty       | [2.64471555e-07] |

# Model

_Type_: kinetic-spectrum

## Initial Concentration

* **input1**:
  * *Label*: input1
  * *Compartments*: ['s1', 's2']
  * *Parameters*: [inputs.s1: **5.00000e-01** *(fixed)*, inputs.s2: **6.81094e-01** *(StdErr: 3e-04 ,initial: 5.00000e-01)*]
  * *Exclude From Normalize*: []

## K Matrix

* **km1**:
  * *Label*: km1
  * *Matrix*: 
    * *('s1', 's1')*: rates.k1: **2.50031e-01** *(StdErr: 5e-05 ,initial: 2.00000e-01)*
    * *('s2', 's2')*: rates.k2: **9.99947e-01** *(StdErr: 2e-04 ,initial: 1.10000e+00)*
  

## Irf

* **irf1** (spectral-multi-gaussian):
  * *Label*: irf1
  * *Type*: spectral-multi-gaussian
  * *Center*: [irf.center: **4.00002e-01** *(StdErr: 6e-06 ,initial: 4.00000e-01)*]
  * *Width*: [irf.width: **5.99785e-02** *(StdErr: 8e-06 ,initial: 5.00000e-02)*]
  * *Normalize*: True
  * *Backsweep*: False
  * *Center Dispersion*: []
  * *Width Dispersion*: []
  * *Model Dispersion With Wavenumber*: False

## Dataset

* **dataset1**:
  * *Label*: dataset1
  * *Megacomplex*: ['complex1']
  * *Initial Concentration*: input1
  * *Irf*: irf1

## Megacomplex

* **complex1** (None):
  * *Label*: complex1
  * *K Matrix*: ['km1']

## Equal Area Penalties

* 
  * *Source*: s2
  * *Source Intervals*: [[0, 1000]]
  * *Target*: s1
  * *Target Intervals*: [[0, 1000]]
  * *Parameter*: area.1: **1.00000e+00** *(fixed)*
  * *Weight*: 0.1
