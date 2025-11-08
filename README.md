# NHANES 2021-2023 Inferential Analytics
This project uses NHANES data to perform inferential statistics using Python in Google Colab by exploring the relationships between various variables.
## Variables
The following variables used in this project were: 

- Marital Status (DMDMARTZ)
- Education Level (DMDEDUC2)
- Age in Years (RIDAGEYR)
- Systolic Blood Pressure (BPXOSY3)
- Diastolic Blood Pressure (BPXODI3)
- Vitamin D Lab Interpretation (LBDVD2LC)
- Hepatitis B Lab Antibodies (LBXHBS)
- Weak/Failing Kidneys (KIQ022)
- Minutes of Sedentary Behavior (PAD680)
- Current Self-Reported Weight (WHD020)

## Analysis
### Question 1:
Is there an association between marital status and education level?

**Variables**: DMDMARTZ (marital status) and DMDEDUC2 (education level)

 **Recoding & Cleaning**:

**Marital status recoded as**:
- Married → 1
- Not married → 0
- Missing/refused/don’t know → NA

**Education level recoded as**:
- Less than bachelor → 1 & 2
- Bachelor+ → 3
- Missing → NaN

 **Test**: Chi-square

**Results & Interpretation**:
- The test shows a statistically significant association (p < 0.05), meaning marital status and education level are related. Married individuals are more likely to have a Bachelors degree compared to those who are not married.

### Question 2: 
Is there a difference in the mean sedentary behavior time between those who are married and those who are not married?

**Variables**: DMDMARTZ (marital status) and PAD680 (sedentary behavior time)

 **Recoding & Cleaning**:

 **Sedentary Behavior Cleaned**:

 - Removed placeholder values 7777, 9999
 - Filtered missing values

 **Test**: Independent t-test

 **Results & Interpretation**:
 - The p-value < 0.05 shows a significant difference between groups. Married and unmarried individuals have a significance differece in the amounts of time that they are sedentary.

### Question 3: 
How do age and marital status affect systolic blood pressure?

 **Variables**: IDAGEYR (age), DMDMARTZ (marital status), and BPXOSY3 (systolic blood pressure).

 **Recoding & Cleaning**:
 Removed missing values in age, marital status, and BP columns

  **Test**: 
  - Pearson correlation for Age vs Systolic BP
  - T-test for Marital Status vs Systolic BP

 **Results & Interpretation**:
- There is a moderate positive correlation between age and systolic BP (r = 0.51, p < 0.001). This means that blood pressure tends to increase as age increases.
- There is no significant difference in systolic BP between married and unmarried individuals (p = 0.595).

### Question 4: 
Is there a correlation between self-reported weight and minutes of sedentary behavior?

 **Variables**: WHD020 (self-reported weight) and PAD680 (sedentary behavior time)

 **Recoding & Cleaning**:

 - Removed placeholder values 7777, 9999
 - Filtered missing values

 **Test**: Pearson correlation

 **Results & Interpretation**:
 - The relationship is statistically significant (p-value < 0.001) but there is a very weak positive correlation between weight and sedentary behavior (r = 0.105). This means that as weight increases, sedentary behavior slightly increases.

### Question 5: Creative Analysis
Is there a difference in the mean sedentary behavior time between individuals with sufficient versus deficient Vitamin D status?

**Variables**: LBDVD2LC (Vitamin D lab interpretation) and PAD680 (sedentary behavior time)

 **Recoding & Cleaning**:
 - **Sufficient** for values indicating adequate Vitamin D
- **Deficient** for values coded as 1
- All other values (including missing or unclear codes) were set to NaN

 **Results & Interpretation**:
 - The difference in sedentary behavior between individuals with sufficient vs. deficient Vitamin D is not statistically significant (p > 0.05). 
 
