# Lecture Notes Data Analysis
## Lecture 1
### Terminology
- the **treatment variable** , also called the **independent variable** , is what we are able to modify and is what causes the changes to other variables
- the **outcome variable** , also called the **dependent variable** , is what we observe and is what is affected by the treatment variable.
- In general, how we select the treatment and control groups will influence the population for which the conclusion is valid.
- Control group is the baseline upon which we will make our decision. These will consist of a group who has not been exposed to the independent variable (mammography vs not in the examples)
- If the groups have related features (for instance a control group with mean age 30 and the other with 40) we may get results which are not accurate. It is common practice to assume that features not being controlled will be randomized when working with large groups.

#### Groups Design
-  A **Randomized Controlled Trial (RCT)** is an experimental design in which treatments are assigned at random. We start with a large enough set of individuals (or “units"), divide them randomly into a treatment group and a control group.
-  By the Law of Large Numbers, we will expect the difference in averages of any relevant feature between the two groups to be fairly small. 
-  **Stratification**: Here, we pre-divide the population into groups and then sample proportionately from each group.
-  A common stratification will be done by splitting patients into groups according to certain demographic categories.
-  The randomized assignment can then be done within each group, which allows for valid inference both within each subgroup or as a whole by aggregating the results across groups.
-  Stratification can result in sample size concers on subtests.

#### Ethical and human considerations
- **Double
blindness**: human subjects are prevented from knowing whether they are in the treatment or control groups. At the same time, whoever is in charge of the experiment and anyone else who could interact with the patient are also prevented from directly knowing whether a patient is in the treatment or the control group. This is to prevent a variety of cognitive biases such as observer bias or confirmation bias that could influence the experiment.
- **Ethical considerations**: Not offering treatment to some people may be unethical. Consent is a major component in modern ethical standards, meaning that it is required for those in the study to understand its parameters and agree to its terms.

#### Observational Study
##### Confounding variables
When randomization is not possible we have to do an observational study.As a result, we are unable to discern whether the difference is from the treatment's effect or from a difference in baseline values.

This phenomenon is called confounding , and **any external variable that can be identified to influence both the treatment and the outcome variables** is called a confounding variable .

 If the confounding variable is a demographic category, then balancing the treatment variable within each category resolves the issue.
 
##### Control variables
In an ideal setting, we select controls that will capture all possible sources of bias, factors that lead to both the treatment and outcome values. Most studies will only identify a subset of these sources, however. After identifying the controls, there are a whole array of techniques to account for their effects, the most common of which is multivariate regression. 

##### Control variable pitfal and casualty
In the diagran we wish to study the relation between smoking and having a stroke. If we use hospitalization as a varible we will get a fake positive relation.
 ![](https://courses.edx.org/assets/courseware/v1/561c113555d3a73f2c310e99502026d0/asset-v1:MITx+6.419x+3T2021+type@asset+block/images_causal_diag.png)
### Bernoulli and Binomial models
The Bernoulli model describes discrete events or their corresponding indicator variables, while the binomial model describes the sum of a fixed number of independent indicator variables. Both models are based on a probability parameter , which corresponds to the probability that a given event occurs. 

 An indicator variable is a random variable that has a corresponding event. The indicator variable takes on the value if the event occurs and the value if the event does not occur.

#### Bernoulli Dist
Bernoulli random variables are used to model random experiments with only two possible outcomes.

E[X] = *p*, var[X] = *p\*(1-p)*

In many applications of the Bernoulli model with multiple indicator variables, they are independent and identically distributed (i.i.d.), meaning that the indicator variables are mutually independent and that they are all Bernoulli with the same parameter *p*.

#### Binomial Dist
The binomial random variable with parameters *n* (trials) and *p* (probability) is defined as the sum of *n* independent Bernoulli random variables, all with parameter *p*.

###### Exercise: binomial_calculation.ipnyb

### Hypothesis Testing
#### 1 Determine a Model
Breast cancer example: X ~ Bernoulli(pi) or Y ~ Poisson(lambda)
#### 2 Determine Null hypothesis and alternative
Null (H<sub>0</sub>): pi = expected p or  lambda = expected lambda

Alternative (H<sub>A</sub>): pi < > <> expected pi (same for lambda)

#### 3 Determine test statistic
T:= Actual Number of Deaths in Control Group

#### 4 Determine significance level
The probability of rejecting H<sub>0</sub>, e.g. alpha = 0.05

This is compared to the p value (area under the curve to the left of the observed value), therefore the smaller the p more significant the result (less chances of the result being just a random outcome).

### Testing Errors and Power of a test
**Type 1**: Rejecting the null hypothesis when in fact it is true (ie finding the observations significant when in reality they are not).

**Type 2**: Accepting the null hypothesis when in realiity the findings are significant.

**Power**: 1 - Prob(TypeII error)

One sided tests have more power, so when possible revert to this kind of tests.