Local Entropy
===

Some notes from watching Zecchina's lectures:

* Local entropy effectively employs a "low pass filter" on rocky energy landscapes
* Many of the gradient descent methods get seduced by a canonical answer from a dense
  region at a higher temperature which becomes an isolated region at lower temperature
* The distance between answers is $O(d)$, meaning it's, in some sense, like an error
  correcting code, where answers are very far away from each other, without wildcard
  variables shared between solutions
* The analogy Zecchina uses is that it's a golf course, with the holes being global
  minima not surrounded by a low energy region but with a lake (presumably also a valid
  global minima) representing the dense local minima, where local entropy selects
  for the lakes
* I suspect one of the reasons why local entropy works for the problems in question
  is that the replicas exploit extreme value like statistics, making it exponentially
  more probably to find a dense region of low entropy
* One method proposed looks to have $y$ replicas (with $y \in \{2,3,4,5\}$) that impose
  a correlation term to make sure the replicas stay within a certain distance of each other

---

Zechinna uses a NN example problem.

Below, $L _ {NE}$ is "Number Error", as in the number of training data
that differ from what the current NN predicts.
I think this can essentially be taken as "energy", with 0 energy being
optimal and higher energy being sub-optimal.

* Local Free Entropy - $\phi(W,\gamma, \beta) = \lg(\sum _ {W'} e^{-\beta L _ {\text NE}  (W') - \frac{\gamma}{2}d(W, W')) } )$
* Large Deviation Partition Function - $Z(y, \gamma, \beta', \beta) = \sum _ W e^{-\beta' L _ {\text NE}(W) + y \phi(W,\gamma, \beta)}$
  - $y \in \mathbb{Z}^+$, (e.g. $y \in \{ 2,3,4,5 \})
* $Z(y,\gamma,\beta',\beta) = \sum _ { W, \{W _ a\} } e ^ { -\beta' L _ { \text NE } ( W) - \beta \sum _ {a=0}^{y-1} L _ {\text NE} (W _ a) - \frac{\gamma}{2} \sum _ {a=0}^{y-1} d(W, W _ a) } $

References
---

* [Learning by Local Entropy Maximization by Riccardo Zecchina](https://www.youtube.com/watch?v=_QZmnQKjzaE)
* [Evidence for local entropy optimization in machine learning, physics and neural networks" by Riccardo Zecchina](https://www.youtube.com/watch?v=nD58NmDvCFo)
* [Riccardo Zecchina - From Spin Glasses theory to Optimization in High Dimensions and Modern ANN](https://www.youtube.com/watch?v=iKv-mNVTg8I)
