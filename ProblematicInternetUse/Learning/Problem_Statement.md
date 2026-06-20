# Overview

Can you predict the level of problematic internet usage exhibited by children and adolescents, based on their physical activity? The goal of this competition is to develop a predictive model that analyzes children's physical activity and fitness data to identify early signs of problematic internet use.

# Description

In today's digital age, problematic internet use among children and adolescents is a growing concern. Better understanding this issue is crucial for addressing mental health problems such as depression and anxiety.

Current methods for measuring problematic internet use in children and adolescents are often complex and require professional assessments.

This competition challenges you to develop a predictive model capable of analyzing children's physical activity data to detect early indicators of problematic internet and technology use. This will enable prompt interventions aimed at promoting healthier digital habits.

# Evaluation

Submissions are scored based on the **quadratic weighted kappa**, which measures the agreement between two outcomes. This metric typically varies from 0 (random agreement) to 1 (complete agreement). In the event that there is less agreement than expected by chance, the metric may go below 0.

To compute the quadratic weighted kappa, we construct three matrices: \(O\), \(W\), and \(E\), with \(N\) the number of distinct labels.

- The matrix \(O\) is an \(N \times N\) histogram matrix such that \(O_{i,j}\) corresponds to the number of instances that have an actual value \(i\) and a predicted value \(j\).

- The matrix \(W\) is an \(N \times N\) matrix of weights, calculated based on the squared difference between actual and predicted values:

  $$
  W_{i,j} = \frac{(i - j)^2}{(N - 1)^2}
  $$

- The matrix \(E\) is an \(N \times N\) histogram matrix of expected outcomes, calculated assuming that there is no correlation between values. This is calculated as the outer product between the actual histogram vector of outcomes and the predicted histogram vector, normalized such that \(E\) and \(O\) have the same sum.

From these three matrices, the quadratic weighted kappa is calculated as:

  $$
  \kappa = 1 - \frac{\sum_{i,j} W_{i,j} O_{i,j}}{\sum_{i,j} W_{i,j} E_{i,j}}
  $$

# Submissions File

For each `id` in the test set, you must predict the corresponding `sii` (described on the Data page). The file should contain a header and have the following format:

```
id,sii
000046df,0
000089ff,1
00012558,2
00017ccd,3
...
```
000089ff,1
00012558,2
00017ccd,3
...

