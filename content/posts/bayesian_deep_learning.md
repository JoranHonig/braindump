+++
title = "Bayesian Deep Learning"
author = ["Jethro Kuan"]
lastmod = 2020-05-31T20:20:05+08:00
tags = ["bayes", "deep-learning"]
draft = false
+++

### Backlinks {#backlinks}

- [Deep Learning With Bayesian Principles - Emtiyaz Khan]({{< relref "emti_dl_with_bayesian_principles" >}})

## The Case For Bayesian Learning <a id="179a446e344f34ef9150164c2bd666ae" href="#wilson2019bayesian">(Wilson, 2019)</a> {#the-case-for-bayesian-learning}

- Vague parameter prior + structured model (e.g. CNN) = structured
  function prior!
- The success of ensembles encourages Bayesians, since ensembles
  approximate the Bayesian Model Average

## Bayesian Perspective on Generalization <a id="b9a995db75df332d755d4fb40282c70d" href="#smith_quoc_bayes_generalization_sgd">(Smith \& Le, 2018)</a> {#bayesian-perspective-on-generalization}

Bayesian model comparisons were first made on Neural Networks by
Mackay. Consider a classification model \\(M\\) with a single parameter
\\(w\\), training inputs \\(x\\) and training labels \\(y\\). We can infer a
posterior probability distribution over the parameter by applying
Bayes theorem:

\begin{equation}
P(w|y,x;M) = \frac{P(y|w,x;M)P(w;M)}{P(y|x;M)}
\end{equation}

The assumption of a Gaussian prior for \\(P(w;M)\\) leads to a posterior
density of the parameter given the new training data \\(P(w|y;x;M)
\propto \sqrt{\lambda/2\pi}e^{-C(w;M)}\\), where \\(C(w;M) = H(w;M) +
\lambda w^2 / 2\\), which is the L2 regularized cross-entropy.

We can evaluate the normalizing constant, \\(P(y|x;M) =
\sqrt{\frac{\lambda}{2\pi}} \int dw e^{-C(w;M)}\\). Assuming that the
integral is dominated by the region near the minimum \\(w_0\\), we can
estimate the evidence by Taylor expanding \\(C(w;M) \approx C(w_0) +
C''(w_0)(w-w_0)^2\\).

\begin{equation}
P(y|x;M) = \mathrm{exp} \left\\{ -\left( C(w_0) +
\frac{1}{2}ln(C''(w_0)/\lambda) \right) \right\\}
\end{equation}

In models with many parameters, \\(P(y|x;M) \approx
\frac{\lambda^{p/2}f^{-C(w_0)}} {| \nabla \nabla C(w) |\_{w_0}^{1 / 2}}\\),
where the denominator can be thought of as an "Occam factor", causing
the network to prefer broad minima.

# Bibliography

<a id="wilson2019bayesian" target="_blank">Wilson, A. G., _The case for Bayesian deep learning_, NYU Courant Technical Report, _()_, (2019). </a> [↩](#179a446e344f34ef9150164c2bd666ae)

<a id="smith_quoc_bayes_generalization_sgd" target="_blank">Smith, S., & Le, Q. V., _A bayesian perspective on generalization and stochastic gradient descent_, In , (pp. ) (2018). : .</a> [↩](#b9a995db75df332d755d4fb40282c70d)

### Backlinks {#backlinks}

- [Deep Learning With Bayesian Principles - Emtiyaz Khan]({{< relref "emti_dl_with_bayesian_principles" >}})
