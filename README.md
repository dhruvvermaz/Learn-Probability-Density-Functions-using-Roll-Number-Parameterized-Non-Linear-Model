# Learn Probability Density Functions using Roll-Number-Parameterized Non-Linear Model

## Objective
The objective of this assignment is to learn the parameters of a probability density function (PDF) using a non-linear transformation of the NO₂ feature from the India Air Quality dataset. The transformation and PDF parameters are dependent on the university roll number.

---

## Dataset
**Dataset Name:** India Air Quality Data  
**Feature Used:** NO₂  
**Dataset Link:** https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data  

---

## Roll Number
**102303116**

---

## Step-1: Non-Linear Transformation

Each value of NO₂ (x) is transformed into a new variable **z** using the transformation function:


z = x + ar sin(br x)


Where:


ar = 0.05 × (r mod 7)  
br = 0.3 × (r mod 5 + 1)


### Calculations for Roll Number 102303116:


r mod 7 = 2  
r mod 5 = 1


Therefore:


ar = 0.05 × 2 = 0.10  
br = 0.3 × (1 + 1) = 0.6


### Final Transformation Used:


z = x + 0.10 sin(0.6x)


This transformation introduces controlled non-linearity into the original NO₂ data while maintaining the structure of the dataset.

## Step-2: Learning PDF Parameters

The probability density function is defined as:
p(z) = c e^(−λ(z−μ)²)

The parameters are estimated using **Maximum Likelihood Estimation (MLE):**


μ = mean(z)  
variance = var(z)  
λ = 1 / (2 × variance)  
c = sqrt(λ / π)


These formulas ensure the PDF is properly normalized and accurately fits the transformed data.

---

## Output Obtained
*(Run the transformation on the dataset to compute these values)*


lambda =  0.0014605747435020783 
mu = 25.8132695310288
c = 0.02156189649281959  


---

## Interpretation

- **μ (mu):** Represents the center of the transformed distribution.  
- **λ (lambda):** Controls the spread of the distribution.  
- **c:** Ensures that the probability density function integrates to 1.

Together, these parameters fully define the learned probability density function for the transformed NO₂ data.

---

## Conclusion

The NO₂ feature was successfully transformed using a roll-number-based non-linear function. The parameters μ, λ, and c can then be estimated using statistical methods such as Maximum Likelihood Estimation. The resulting PDF models the distribution of the transformed air quality data effectively.
