# Stroop-Effect
In this project, a classic phenomenon from experimental psychology called the Stroop Effect will be investigated. An overview of the experiment will be provided, hypothesis will be created regarding the outcome of the task. Some data collected from people who have performed the same task will be analyzed and some statistics describing the results will be computed. Finally, the results will be interpreted in terms of the hypotheses defined.

# Background information

In a Stroop task, participants are presented with a list of words, with each word displayed in a color of ink. The participant’s task is to say out loud the color of the ink in which the word is printed. The task has two conditions: a congruent words condition, and an incongruent words condition. In the congruent words condition, the words being displayed are color words whose names match the colors in which they are printed: for example RED, BLUE. In the incongruent words condition, the words displayed are color words whose names do not match the colors in which they are printed: for example PURPLE, ORANGE. In each case, we measure the time it takes to name the ink colors in equally-sized lists. Each participant will go through and record a time from each condition.
Questions

**Question 1:** What is our independent variable? What is our dependent variable?

    Independent variable: Condition (congruent/incongruent)
    Dependent variable: Time of reaction of participants to name the colour of words

**Question 2:** What is an appropriate set of hypotheses for this task? What kind of statistical test do you expect to perform? Justify your choices.

H0 refers to the null hypothesis and HA refers to the alternate hypothesis. μi refers to the population mean of incongruent tasks and μc refers to the population mean of incongruant tasks.

    H0: ( μi - μc = 0 ) - Time to name colours is the same for congruent and incongruent tasks
    HA: ( μi - μc ≠ 0 ) - Time to name colours is not the same for congruent and incongruent tasks

These hypotheses were chosen because they define whether the Stroop Effect exists. The dependent samples t-Test is the appropriate statistical test, as the same subjects are assigned two different conditions. The different conditions are dependent because by performing the first test, participants develop their abilities and might have an unfair advantage due to the learning effect. In addition, there are no population parameters provided (so a z-test would not be appropriate in this case. The sample is composed of 24 participants that performed the test two times, one with congruent and one with incongruent words).

**Question 3:** Report some descriptive statistics regarding this dataset. Include at least one measure of central tendency and at least one measure of variability.

'''
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import pdb

Datacolor = pd.read_csv('Desktop/stroopdata.csv')
Datacolor.head().round(2)
'''

	Congruent 	Incongruent
0 	12.08 	19.28
1 	16.79 	18.74
2 	9.56 	21.21
3 	8.63 	15.69
4 	14.67 	22.80

Datacolor.describe().round(2)

	Congruent 	Incongruent
count 	24.00 	24.00
mean 	14.05 	22.02
std 	3.56 	4.80
min 	8.63 	15.69
25% 	11.90 	18.72
50% 	14.36 	21.02
75% 	16.20 	24.05
max 	22.33 	35.26

**Question 4:** Provide one visualization that show the distribution of the sample data. Write one or two sentences noting what you observe about the plot or plots.

%pylab inline
import matplotlib.pyplot as plt
Datacolor.plot.bar()
sns.plt.title('Distribution of Congruent and Incongruent Data')
plt.ylabel("Time")
plt.xlabel("Frequency")

Populating the interactive namespace from numpy and matplotlib

<matplotlib.text.Text at 0x115591550>

The grapg above shows that the incongruent tasks takes more time than the congruent tasks. There are two outliers for incongruent words at around 35 seconds.

**Question 5:** Now, perform the statistical test and report your results. What is your confidence level and your critical statistic value? Do you reject the null hypothesis or fail to reject it? Come to a conclusion in terms of the experiment task. Did the results match up with your expectations?

Confidence level = 99%

Alpha = .01

t-critical two-tailed = +-2.807

t-statistic = -8.021

r² = .737

The t-statistic (-8.021) is lower than the negative t-critical (-2.807), therefore the null hypothesis is rejected.

This result means that the difference between the congruent and incongruent samples is statistically significant. According to the r², 73.70% of this difference is due to the words condition (congruent or incongruent). The results match my expectations.

**Question 6:** Optional: What do you think is responsible for the effects observed? Can you think of an alternative or similar task that would result in a similar effect? Some research about the problem will be helpful for thinking about these two questions!

The brain associates the shape of the word and the colour. When there is a mismatch, additional time is necessary for the prefrontal cortex to process information and interpret them. A similar effect would likely be observed if the participants were shown words of the correct colour but the wrong text.

# References

    https://docs.google.com/document/d/1-OkpZLjG_kX9J6LIQ5IltsqMzVWjh36QpnP2RYpVdPU/pub?embedded=True
    https://drive.google.com/file/d/0B9Yf01UaIbUgQXpYb2NhZ29yX1U/view
    https://en.wikipedia.org/wiki/Stroop_effect

