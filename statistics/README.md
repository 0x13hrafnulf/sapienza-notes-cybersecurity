# Statistics

[[_TOC_]]

## Practice

- [Website](https://mazzinistatistics.wordpress.com/)
- [Website's repo](https://gitlab.com/myasnik/sapienza-statistics-homeworks)

## Theory

### Lesson 1: Intro

#### Descriptive statistics

  ![](./res/img/1.png)

  ![](./res/img/2.png)

#### Inferential statistics

- From smaller set i infer something about a larger set

  ![](./res/img/3.png)

#### Descriptive vs Inferential statistics

- Inferential is an extension of the descriptive

  ![](./res/img/4.png)

#### Univariate and Multivariate statistics

- Both can be descriptive and inferential, univariate can be expanded to multivariate
  - Univariate: just one attribute
    - Example

      ![](./res/img/5.png)

  - Multivariate: more attributes

#### Distribution

- Ideal goal of statistics: describe the distribution of the population either in case of a know one (descriptive statistics) or unknown (inferential statistics)
- Types
  - Empirical
    - Grouping and counting to get **relative frequencies** (n over the total)

      ![](./res/img/6.png)

    - How to

      ![](./res/img/9.png)

    - Example
      - Uniform

        ![](./res/img/7.png)

      - In this other case 60 can be considered in two different places so we must decide which is the correct one (using parenthesis)

        ![](./res/img/8.png)

  - Theoretical
    - Inferential statistics is strictly connected with it

### Lesson 2: Intro

#### Attribute vs Variable

![](./res/img/10.png)

- While an attribute is often intuitive, the variable is the operationalized (define the values that a variable can take) way in which the attribute is represented for further data processing
- Example
  - Attribute: age
  - Variable: young, old

#### Variable types

- Qualitative
  - Ordinal: we can define a scale of importance

    ![](./res/img/11.png)

  - Nominal: can't define a scale of importance (example: hair color)
- Quantitative
  - Interval
  - Ratio

#### Time series analysis

![](./res/img/12.png)

- There is always an order and time is infinite so time is always imaginable as part of a larger set

![](./res/img/13.png)

#### Spatial data analysis

- Data analysis performed on space (ex: regions)
- Can be ordered on a lot of factors (latitute, longitude...)

#### Statistical data in real world

![](./res/img/14.png)

#### Stream processing vs store processing (batch processing)

![](./res/img/15.png)

- One pass: single passage on the data is required to compute
- Multi pass: multiple passage on the data is required to compute
- Offline algorithm: data is stored
- Online algorithm: data can be a stream from the net

#### Random, timer and collections

- Random: generates random number
- Timer: ticks every x time
- Collections: list, array, dictionary...

#### Average as a representative value

- Average **represents** the "going" of something

#### Metadata

![](./res/img/16.png)

- Metadata gives context to an analysis
- An object contains data and metadata

#### Knuth's formula (average with stream processing, running mean)

![](./res/img/17.png)

![](./res/img/13.png)

- Always use this formula, never the naive formula!!!

### Lesson 3: Frequency and probability

- We substitute (in inferential statistic) the relative frequency of a variable with its probability

  ![](./res/img/19.png)

#### Bivariate distribution

![](./res/img/20.png)

  - Marginal distribution: right and down parts of the table, define distribution of Y and X

- Conditional distribution (rows and cols): in the example defines the distribution of the height (Y) on the `[60 -70]` weight group (X1)

  ![](./res/img/21.png)

  ![](./res/img/22.png)

- Contingency table: table that represent the bivariate distribution

#### Correlation between bivariate relative frequency and univariate relative frequency

![](./res/img/23.png)

![](./res/img/24.png)

![](./res/img/25.png)

![](./res/img/26.png)

  - So `conditional frequency = joint frequency / marginal frequency` and`conditional probability = joint probability / marginal probability`

#### Explanation of probability of an intersection, conditional probability and independence

![](./res/img/27.png)

![](./res/img/28.png)

![](./res/img/29.png)

![](./res/img/30.png)

![](./res/img/32.png)

![](./res/img/33.png)

![](./res/img/34.png)

![](./res/img/35.png)

![](./res/img/31.png)

![](./res/img/36.png)

![](./res/img/37.png)

#### Statistical independence

- Strong correlation

  ![](./res/img/38.png)

- Independence

  ![](./res/img/39.png)

  - Condition for independence

    ![](./res/img/40.png)

    ![](./res/img/41.png)

    ![](./res/img/42.png)

  - So joint frequency (same for joint probability):

    ![](./res/img/43.png)

    ![](./res/img/44.png)

- Kolmogorov says that defining properties of probability is equal to defining properties for the relative frequency

### Lesson 4: Summary statistics

#### Summary statistics

- Summary statistics: any function applied to the dataset (it's summaryzing an aspect of the dataset)
  - Example
    - Mean
    - Median
    - Mode
    - Standard deviation
    - Variance
    - Mean absolute deviation
    - ...

#### Measure of central tendency

- Measure of central tendency: summarize more or less how values are placed on a "line"
  - Example (mean)

    ![](./res/img/45.png)

  - Types
    - Mean (quantitative)
    - Median (ordinal): value of X such that 50% of the observations are <= median and 50% are >= median

      ![](./res/img/46.png)

      ![](./res/img/47.png)

    - Mode (nominal): most frequent value

      ![](./res/img/48.png)

      ![](./res/img/49.png)

#### Measure of dispersion

- Measure of dispersion: how close are the x to my measure of central tendency

  ![](./res/img/50.png)

  ![](./res/img/51.png)

  - Types
    - Variance (mean squared deviation) and mean absolute deviation

      ![](./res/img/52.png)

      ![](./res/img/53.png)

    - Standard deviation

      ![](./res/img/54.png)

    - Range
    - ...

#### Variance online algorithm (Welford)

![](./res/img/55.png)

- Recall online mean

  ![](./res/img/56.png)

  ![](./res/img/57.png)

- Identity for variance

  ![](./res/img/58.png)

  - In other words, like this we demonstrate that the best value with respect to we have to calculate the "distance" is, in fact, the mean!
- So, the online algorithm for variance is explained like this:

  ![](./res/img/59.png)

  ![](./res/img/60.png)

#### Measures of shape

![](./res/img/61.png)

- Types
  - Skewness: measures the asymmetry (the higher is, the higher is asymmetry)
  - Kurtosis: the higher is, the more frequency you have on the tails

#### Covariance

- Covariance: linear relationship between two variables (measure the correlation)

  ![](./res/img/62.png)

    - We can consider the variance as the covariance of X with itself
- Example of how covariance works

  ![](./res/img/63.png)

  - So, if we have a covariance that is "more positive" this means that the points are placed on the "positive line" (direct relationship), else the opposite (inverse relationship)

    ![](./res/img/64.png)

    ![](./res/img/65.png)

    - Direct: to more positive values of x you have more positive values of y
    - Inverse: to more positive values of x you have more negative values of y
- Online algorithm and correlation with variance

  ![](./res/img/66.png)

#### Coefficient of correlation

  ![](./res/img/67.png)

#### General mean

![](./res/img/70.png)

- Types
  - Arithmetic: h = 1
  - Quadratic: h = 2

    ![](./res/img/69.png)

  - Harmonic: h = -1

    ![](./res/img/71.png)

  - Geometric: r -> 0

    ![](./res/img/68.png)

#### Distance

- Given different types of distances we can compute an `x_c` that minimize those distances; this `x_c` is 100% of times the "Middle value" 

  ![](./res/img/72.png)

  - For the mean the correct word is "premetric" and not distance

#### Variance and covariance naive formula

- Covariance

  ![](./res/img/73.png)

  ![](./res/img/74.png)

- Variance

  ![](./res/img/75.png)

#### Regression

- Regression is finding the distance (premetric) but we are in a multivariate case

##### Linear regression (bivariate)

  ![](./res/img/76.png)

- Ordinary least squares (OLS)

  ![](./res/img/77.png)

- Regression line

  ![](./res/img/80.png)

    - We want to minimize a and b, the final line has this shape:

      ![](./res/img/78.png)

- There are two regression lines: one nearer to x, one to y
  - Regression lines are coincident if points are perfectly aligned

    ![](./res/img/79.png)

##### Variance Decomposition and Coefficient Of Determination

![](./res/img/81.png)

![](./res/img/82.png)

- Coefficient of determination: the name is `R^2`

![](./res/img/83.png)

### Lesson 5: Probability

#### Measure theory vs Probability theory

- By Kolmogorov
  - Probability is just a measure between 0 and 1 (probability theory is a subset of the measure theory)
- Measure theory
  - A measure is positive
  - It is 0 for the empty set
  - Countable additivity

    ![](./res/img/87.png)

    - Even if they are infinite
- Probability theory
  - Same as measure theory
  - Falls in 0 - 1 (probability of at least one of the events is 1)
- Measure space

  ![](./res/img/85.png)

  - A probability space is the same but with different letters (see next)
- Power set: set of all subset of a given set including the empty set and the set itself
- Sigma-algebra: subset of power set that satisfies
  - Must contain the set itself
  - Closed with respect to the complement
  - Closed with respect to the union
- Parallelism: measure theory and probability theory

  ![](./res/img/84.png)

  ![](./res/img/86.png)

#### Parametric inference

![](./res/img/88.png)

- We want to find what values of parameters (given that we can choose various and different parameters, theta, states of nature) of the family are more likely to generate the empirical distribution: this is parametric inference (or parametric statistics)

  ![](./res/img/89.png)

  ![](./res/img/90.png)

- Most important theoretical distribution model: normal distribution
  - Example of parametric inference using the normal distribution as the family of theoretical distribution

    ![](./res/img/91.png)

    - I want to find which is the pair of state of natures more probable given the empirical distribution E

      ![](./res/img/92.png)

      ![](./res/img/93.png)

      - We know the likelihood!

        ![](./res/img/94.png)

#### Inductive reasoning

![](./res/img/95.png)

- Which one is more probable?

  ![](./res/img/96.png)

#### Role of probability in statistics

- Probability in the end is relative frequency; all axioms of probability are also true for relative frequency
- Again, relative frequency is just the materialization of the abstract model which is the probability

  ![](./res/img/97.png)

  - This is inferential statistics
- Goal of inference

  ![](./res/img/99.png)

  ![](./res/img/100.png)

- Symmetry between inference and relative frequency

  ![](./res/img/98.png)

#### Probability space

- Probability space

  ![](./res/img/101.png)

  ![](./res/img/102.png)

  - P is the measure of the event space (space of all the probabilities, for each event space event)

#### Random variable

  ![](./res/img/103.png)

- Informally: a random variable is a variable with a probability attached
- Formally

  ![](./res/img/104.png)

- CDF and PDF
  - Cumulative distribution function (CDF)

    ![](./res/img/105.png)

  - PDF is the derivative of CDF, CDF is the integral of PDF

    ![](./res/img/107.png)

- Generation of random variable distribution

  ![](./res/img/106.png)

  - Given the uniform distribution u in 0-1 (random number generator in 0-1), applying to the generated number the inverse of F we obtain a (in this case) negative exponential distribution
  - Why?

    ![](./res/img/107.png)

    ![](./res/img/108.png)

#### Lebesgue integral and mean, variance of random variables

- Probability: theoretical vs empirical

  ![](./res/img/109.png)

  - Inference: passing from empirical to theoretical (generalization)
- Conditional frequency, statistical independence, mean and variance are empirical concepts that can be translated to the theoretical model
  
  ![](./res/img/110.png)

  ![](./res/img/111.png)

  ![](./res/img/112.png)

  ![](./res/img/113.png)

  - For continuous random variables this is the formula
  - Dividing mean in two different formulas based on the continuity/discreet fo the random variable is not done anymore, now Lebesgue-Stielties integral is used
- Lebesgue-Stielties integral
  - Lebesgue works in a measure space, so is more general!
  - Lebesgue vs Riemann (classic integral used for continuous random variables)

    ![](./res/img/114.png)

  - Lebesgue general formula (mean)

    ![](./res/img/115.png)

    - Why?

      ![](./res/img/117.png)

      ![](./res/img/118.png)

      ![](./res/img/119.png)

  - Lebesgue general formula (variance)

    ![](./res/img/116.png)

### Lesson 6: Convergence

#### Sequences Of Random Variables

- Given a simple random variable (ex: bernoulli, i hit or miss a tag)

  ![](./res/img/120.png)

- A sequence of random variables is simply considering more random variables together

  ![](./res/img/121.png)

  - When this sequence has variables with same probability distribution (in this case probability of variables is always the same) it is called identically distributed
  - When the probability of the intersection of all the variables is the general product those variables are called independent
  - Usually we will be in this case but a sequence can be nor independent or identically distributed

#### Convergence In Distribution

![](./res/img/122.png)

![](./res/img/123.png)

- In this example, will the frequency (with n -> inf) stabilize near a value or it will continuously oscillate between 0 and 1?

  ![](./res/img/124.png)

- This is called convergence in distribution

  ![](./res/img/125.png)

#### Convergence in probability

![](./res/img/126.png)

- The probability of "going outside the street" (tails of curves) going to infinity comes to 0
  - For a Bernoulli random variable this converges to P (law of large numbers)

    ![](./res/img/127.png)

    - This is called weak convergence (probability convergence)
- There are various types of convergence

  ![](./res/img/128.png)

  - Almost sure (a.s.) convergence implies convergence in probability which implies convergence in distribution
- So, for the law of large numbers (LLN) we create a link between relative frequency and probability: going to infinite the relative frequency converges to the probability

  ![](./res/img/129.png)

#### Almost sure convergence

- Going to infinite the paths that go outside the street are 0

  ![](./res/img/130.png)

- This is called strong convergence
- So there are two LLNs

  ![](./res/img/131.png)

#### Mean in convergence (mean of a sample mean)

![](./res/img/132.png)

#### Variance in convergence (variance of a sample mean)

![](./res/img/133.png)

### Lesson 7

#### Concentration Inequalities

- Definition: bounds to distributions (statistical and also of random variables)

##### Markov inequality
  
- Definition: provide an upper bound knowing the average

  ![](./res/img/134.png)

- I must consider `k` that is larger than the mean
- Example

  ![](./res/img/135.png)

  - Frequency of 25, 25, 29 is certainly less than 93.2%
  - Pretty simple knowing values, but if we just know the mean is useful!
  - Example proof

    ![](./res/img/136.png)

    ![](./res/img/137.png)

    ![](./res/img/138.png)

    ![](./res/img/139.png)

    ![](./res/img/140.png)

    ![](./res/img/141.png)

    ![](./res/img/142.png)

    - Same proof can be done for random variables

##### Chebyshev inequality (from Markov inequality)

![](./res/img/143.png)

![](./res/img/144.png)

- Definition: probability on the tails is certainly lower than `1/a^2`

  ![](./res/img/145.png)

  - (Error) Sigma is squared
- From this the Law of Large Numbers arises

  ![](./res/img/146.png)

  ![](./res/img/147.png)

#### Almost sure convergence

- In convergency probability (weak LLN) am i sure that paths will never go beyond the limits defined by epsilon? NO

  ![](./res/img/148.png)

  - To say this i need almost sure convergence (strong LLN): i am sure that i won't go beyond the epsilon limits infinite number of times but just a finite number of times and for an `n` sufficiently large the bounds will be completely respected
- To recap

  ![](./res/img/149.png)

- Proof (Borel-Cantelli)

  ![](./res/img/150.png)

  - Also the opposite is true

#### Glivenko-Cantelli theorem

- Recall: CDF

  ![](./res/img/151.png)

- Convergence of empirical CDF to theoretical CDF

  ![](./res/img/152.png)

  ![](./res/img/153.png)

  ![](./res/img/154png)

- Glivenko-Cantelli theorem refines this result: uniform convergence instead of point-wise convergence
  - What is uniform and point-wise convergence
    - Uniform: the line gets nearer to `y = x` uniformly

      ![](./res/img/155.png)

    - Not uniform (point-wise): convergence is not the same for all the points of the line

      ![](./res/img/156.png)

    - Point-wise vs uniform

      ![](./res/img/157.png)

      - Uniform: for all x

        ![](./res/img/158.png)

      - Point-wise: for each x

        ![](./res/img/159.png)

#### Standardization

![](./res/img/160.png)

- Property of deviation

  ![](./res/img/161.png)

  ![](./res/img/162.png)

  - With deviation we could compare two statistical populations that are completely different? Yes but actually no (variance could be different)

    ![](./res/img/163.png)

    ![](./res/img/164.png)

    - Solution: z score eliminates those differences

      ![](./res/img/165.png)

- Standardization: used to "center" variables to make comparisons
- As we have seen in the simulation (random vars converging to `p`) the convergence degenerates to one point (`p`)

  ![](./res/img/166.png)

  - Standardizing this variable (so the variance is equal to 1) we will not make the simulation degenerate

    ![](./res/img/167.png)

    - Or like this, the important is that the variance doesn't oscillate but is constant

      ![](./res/img/168.png)

    - Subtracting the mean we will center into the origin

      ![](./res/img/169.png)

    - Doing this we end up with a standard normal distribution (central limit theorem, CLT)

      ![](./res/img/170.png)

      ![](./res/img/171.png)

### Lesson 8

#### Probability zero

![](./res/img/172.png)

- In continuous uniform distribution the probability of an event `e` MUST be zero; continuous distribution is "infinite", so even if `P(e) = epsilon` (where epsilon is a very small number) then the sum of all events probability will exceed 1 (impossible!)
- So having an event with probability 0 doesn't mean that this event is impossible
- We could also have a countable union of probabilites of events which is equal to zero
- In continuous probability infact we use the probability of an interval (more interesting)
- But also in discrete uniform we could have an event with probability zero which could still be possible
- Empty set is the impossible event; still has probability 0

#### Almost sure

- We can revise the almost sure meaning knowing the "probability zero"

  ![](./res/img/173.png)

  - Probability of the complementary is zero but is not impossible!
- Example
  - Imagine throwing a dart at a unit square (a square with an area of 1) so that the dart always hits an exact point in the square, in such a way that each point in the square is equally likely to be hit
  - Since the square has area 1, the probability that the dart will hit any particular subregion of the square is equal to the area of that subregion
  - For example, the probability that the dart will hit the right half of the square is 0.5, since the right half has area 0.5
  - Next, consider the event that the dart hits exactly a point in the diagonals of the unit square
  - Since the area of the diagonals of the square is 0, the probability that the dart will land exactly on a diagonal is 0
  - That is, the dart will almost never land on a diagonal (equivalently, it will almost surely not land on a diagonal), even though the set of points on the diagonals is not empty, and a point on a diagonal is no less possible than any other point

#### Order statistics

![](./res/img/174.png)

![](./res/img/175.png)

- Useful to find median

#### Generalizing order statistics - Quantiles

![](./res/img/176.png)

- For example the median is a quantile with `q = 2`

![](./res/img/177.png)

- Going from left to right it becomes `2/q, 3/q...`
- Definition

  ![](./res/img/178.png)

- Example

  ![](./res/img/179.png)

#### Generalized inverse

- P-quantile: i want to find a quantile so that the probability on the left is at least `P`

  ![](./res/img/180.png)

  ![](./res/img/181.png)

  ![](./res/img/182.png)

  - The quantile function is just the inverse of the CDF (generalized inverse)

    ![](./res/img/183.png)

#### Density (PDF) in order statistics

- Minimum and maximum

  ![](./res/img/184.png)

- General case

  ![](./res/img/185.png)

#### CDF in order statistics

- Minimum

  ![](./res/img/186.png)

- Maximum

  ![](./res/img/187.png)

- General

  ![](./res/img/188.png)

#### Rank order statistics (ranks)

- Place occupied in the order sample with respect to te empirical sample

  ![](./res/img/189.png)

- Coefficient of correlation of rankings

  ![](./res/img/190.png)

- Handling ties (mid-rank method)

  ![](./res/img/191.png)

### Lesson 9

#### Stochastic process definition

- Recall
  - Probability space is a measure space (P is the measure)

    ![](./res/img/197.png)

  - Measurable space

    ![](./res/img/198.png)

  - Random variable: measurable function from omega to a measurable space (real line)

    ![](./res/img/199.png)    

- Definitions
  - Empirical

    ![](./res/img/196.png)

  - Formal: a stochastic process is a function from the set T of indexes (finite, infinite, countable, uncountable...) to the multiset (because we can have repetitions, surjetive but not injective) X of random variables all from the same probability space
    
    ![](./res/img/192.png)
    
    - When indexes are discrete: discrete time process (if T is countable)
      - Example: random walk
    - When indexes are continuous: continuous time process (if T is not countable)
      - Example: poisson process

    ![](./res/img/193.png)

    - Alternative: an indexed family of random variables

#### Discrete/Continuous state process

- Definitions
  - Discrete: random variables are discrete
  - Continuous: random variables are continuous
- We can combine these with discrete/continuous time process

  ![](./res/img/194.png)

  ![](./res/img/195.png)

#### Stochastic process and sample paths

![](./res/img/200.png)

- Parallelism between random variables and random (stochastic) processes

  ![](./res/img/201.png)

  ![](./res/img/202.png)

#### Examples of stochastic processes

![](./res/img/203.png)

#### Stationary increment

- Increment: increment (or decrement) of the random walk in the interval specified

  ![](./res/img/204.png)

  - It is itself a random variable because it is a sum of random variables
  - Mean: sum of the means of the variables in the interval
  - Variance: sum of the variances of the variables in the interval
    - The larger is the interval the larger is the variance
  - **Stationary increment**: the distribution generated is not affected by the interval starting point considered, it is only affected by the size of the interval; all the increments with same interval size have same distribution

#### Continuity

- In probability

  ![](./res/img/205.png)

  ![](./res/img/206.png)

  - Like that the point s converges to the point t
- Almost sure

  ![](./res/img/207.png)

  - I can make this quantity smaller the more i go near to the point t
  - No matter how much epsilon is small, i will always find an s in which the difference with t is smaller than epsilon

#### CADLAG process

- Mandatory properties

  ![](./res/img/208.png)

- Example of CADLAG: CDF

  ![](./res/img/209.png)

#### Levy processes

- Note: as for the central limit theorem every var collapses to a N(0,1), in stochastic processes we collapse to a Brownian motion
- Mandatory properties
  - Continuity in probability
  - X0 = 0
  - Stationary increment
  - Independence of the increments: fo all choices of n and t increments must be independent (joint probability = product of probabilities)

    ![](./res/img/210.png)

#### Brownian motion (Wiener process)

- Properties
  - Same as Levy processes (plus the continuity is almost surely)
  - The distribution of the increment must be a normal

    ![](./res/img/211.png)

![](./res/img/212.png)

### Lesson 10

#### Generalized Brownian motion

![](./res/img/213.png)

- Brownian motion structure (formula)

  ![](./res/img/214.png)

  - Standardization vs generalized

    ![](./res/img/215.png)

  - Definition using increments (Stochastic differential equation, SDE)

    ![](./res/img/216.png)

    ![](./res/img/217.png)

    - In our homeworks we just simulated this SDE
- Brownian motion is the basic building block for other types of stochastic processes

#### Geometric Brownian motion

- In finance absolute (arithmetic) increment is useless, we have to use relative (geometric)

  ![](./res/img/218.png)

  ![](./res/img/219.png)

#### Solving an SDE

- Given an initial point and an SDE we can find a solution; in this case we are considering a general stochastic process (Brownian motion), the solution is the sum of its random variables
  
  ![](./res/img/220.png)

  ![](./res/img/222.png)

- Solving the standard Brownian motion

  ![](./res/img/221.png)

  ![](./res/img/223.png)

- Solving the general Brownian motion

  ![](./res/img/224.png)

#### Ornstein Uhlenbeck and Vasicek SDE

- Ornstein Uhlenbeck SDE: prices of materials tend to return to their initial price (like an elastic force, F = -kx)

  ![](./res/img/225.png)

  - Tendency to return to 0
- Vasicek SDE: generalization of Ornstein Uhlenbeck SDE

  ![](./res/img/226.png)

  - Tendency to return to P

#### Euler Maruyama Method

- What is: method to find a solution to an SDE; it is what we are doing with our simulations

  ![](./res/img/227.png)