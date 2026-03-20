---
title: "H3+ Deuteration Rate Derivation"
layout: default
permalink: /rate-derivation/
nav_exclude: true
---

# H\\(_3^+\\) Deuteration Rate Derivation

This page derives the integrated rate equations for the deuteration of H\\(_3^+\\) as studied in [Hugo et al. (2009)](http://dx.doi.org/10.1063/1.3089422). These equations are used in the [Week 5]({{ "/weeks/5" | relative_url }}) notebook.

## Overview

In Hugo et al. 2009, the deuteration of H\\(_3^+\\) was investigated in an ion trap at 13.5 K. The key reactions and their rates are:

| Reaction | Rate (cm\\(^{-3}\\) s\\(^{-1}\\)) |
| --- | --- |
| H\\(_3^+\\) + HD \\(\to\\) H\\(_2\\)D\\(^+\\) + H\\(_2\\) | \\(k_1^{(2)}[\text{HD}][\text{H}_3^+]\\) |
| H\\(_2\\)D\\(^+\\) + HD \\(\to\\) D\\(_2\\)H\\(^+\\) + H\\(_2\\) | \\(k_2^{(2)}[\text{HD}][\text{H}_2\text{D}^+]\\) |
| D\\(_2\\)H\\(^+\\) + HD \\(\to\\) D\\(_3^+\\) + H\\(_2\\) | \\(k_3^{(2)}[\text{HD}][\text{D}_2\text{H}^+]\\) |

In these equations, brackets indicate the number density (cm\\(^{-3}\\)), and the \\(k_n^{(2)}\\) refer to second-order rate coefficients in units of cm\\(^3\\) s\\(^{-1}\\) so that the rate has units of cm\\(^{-3}\\) s\\(^{-1}\\). At the low temperature, the reverse reactions are negligible. Furthermore, under the experimental conditions, HD is present in excess, and it is reasonable to treat [HD] as constant. Under these pseudo-first-order conditions, we can redefine the rate coefficients:

\\[ k_n \equiv k_n^{(2)}\[\text{HD}\] \\]

Using the rates above, we obtain a set of coupled differential equations describing the time evolution of the number densities:

\\[ \frac{\text{d}\[\text{H}_3^+\]}{\text{d}t} = -k_1\[\text{H}_3^+\] \\]

\\[ \frac{\text{d}\[\text{H}_2\text{D}^+\]}{\text{d}t} = k_1\[\text{H}_3^+\] - k_2\[\text{H}_2\text{D}^+\] \\]

\\[ \frac{\text{d}\[\text{D}_2\text{H}^+\]}{\text{d}t} = k_2\[\text{H}_2\text{D}^+\] - k_3\[\text{D}_2\text{H}^+\] \\]

\\[ \frac{\text{d}\[\text{D}_3^+\]}{\text{d}t} = k_3\[\text{D}_2\text{H}^+\] \\]

## Solving for [H\\(_3^+\\)]

Solving for \\(\[\text{H}_3^+\](t)\\) involves a standard first-order integrated rate equation. Rearranging the first equation above:

\\[ \frac{\text{d}\[\text{H}_3^+\]}{\[\text{H}_3^+\]} = -k_1\,\text{d}t \\]

Integrating both sides:

\\[ \ln \[\text{H}_3^+\](t) = -k_1 t + C \implies \[\text{H}_3^+\](t) = Ae^{-k_1 t} \\]

At \\(t=0\\), \\(\[\text{H}_3^+\] = \[\text{H}_3^+\]_0\\), so \\(A = \[\text{H}_3^+\]_0\\) and:

\\[ \boxed{\[\text{H}_3^+\](t) = \[\text{H}_3^+\]_0\, e^{-k_1 t}} \\]

## Solving for [H\\(_2\\)D\\(^+\\)]

To solve for the time evolution of \\(\[\text{H}_2\text{D}^+\]\\), we substitute the result above into the second rate equation and rearrange:

\\[ \frac{\text{d}\[\text{H}_2\text{D}^+\]}{\text{d}t} + k_2\[\text{H}_2\text{D}^+\] = k_1\[\text{H}_3^+\]_0\, e^{-k_1 t} \\]

To make progress, we introduce an integrating factor \\(\mu \equiv e^{k_2 t}\\), so \\(\text{d}\mu/\text{d}t = k_2 e^{k_2 t}\\). Multiplying both sides by \\(\mu\\):

\\[ \mu\frac{\text{d}\[\text{H}_2\text{D}^+\]}{\text{d}t} + \[\text{H}_2\text{D}^+\]\frac{\text{d}\mu}{\text{d}t} = k_1\[\text{H}_3^+\]_0\, e^{-(k_1-k_2)t} \\]

The left-hand side is recognized as a product rule derivative, so we can write and integrate:

\\[ \frac{\text{d}}{\text{d}t}\left(\mu\[\text{H}_2\text{D}^+\]\right) = k_1\[\text{H}_3^+\]_0\, e^{-(k_1-k_2)t} \\]

\\[ \mu\[\text{H}_2\text{D}^+\](t) = \frac{k_1\[\text{H}_3^+\]_0}{k_2 - k_1}\,e^{-(k_1-k_2)t} + C \\]

Dividing by \\(\mu = e^{k_2 t}\\):

\\[ \[\text{H}_2\text{D}^+\](t) = \frac{k_1\[\text{H}_3^+\]_0}{k_2 - k_1}\,e^{-k_1 t} + Ce^{-k_2 t} \\]

Applying the boundary condition \\(\[\text{H}_2\text{D}^+\] = 0\\) at \\(t=0\\) gives \\(C = -k_1\[\text{H}_3^+\]_0/(k_2 - k_1)\\). Substituting back:

\\[ \boxed{\[\text{H}_2\text{D}^+\](t) = \frac{k_1\[\text{H}_3^+\]_0}{k_2 - k_1}\left(e^{-k_1 t} - e^{-k_2 t}\right)} \\]

Note that if \\(k_1 = k_2 \equiv k\\), the denominator goes to zero and this form is undefined. In that case, the right-hand side of the equation to integrate simplifies to the constant \\(k\[\text{H}_3^+\]_0\\):

\\[ \mu\[\text{H}_2\text{D}^+\](t) = k\[\text{H}_3^+\]_0\, t + C \implies \[\text{H}_2\text{D}^+\](t) = \[\text{H}_3^+\]_0\, kte^{-k t} + Ce^{-kt} \\]

Applying \\(\[\text{H}_2\text{D}^+\] = 0\\) at \\(t=0\\) gives \\(C=0\\), so:

\\[ \boxed{\[\text{H}_2\text{D}^+\](t) = \[\text{H}_3^+\]_0\, kt\,e^{-k t}, \qquad (k = k_1 = k_2)} \\]

## Solving for [D\\(_2\\)H\\(^+\\)]

The procedure is the same as for \\(\[\text{H}_2\text{D}^+\]\\). Substituting the result for \\(\[\text{H}_2\text{D}^+\](t)\\) (assuming \\(k_1 \neq k_2\\)) into the rate equation for \\(\[\text{D}_2\text{H}^+\]\\) and rearranging:

\\[ \frac{\text{d}\[\text{D}_2\text{H}^+\]}{\text{d}t} + k_3\[\text{D}_2\text{H}^+\] = \frac{k_1 k_2\[\text{H}_3^+\]_0}{k_2 - k_1}\left(e^{-k_1 t} - e^{-k_2 t}\right) \\]

Introducing the integrating factor \\(\mu \equiv e^{k_3 t}\\) and applying the same product-rule and integration steps:

\\[ \mu\[\text{D}_2\text{H}^+\](t) = \frac{k_1 k_2\[\text{H}_3^+\]_0}{k_2 - k_1}\left(\frac{e^{-(k_1-k_3)t}}{k_3 - k_1} - \frac{e^{-(k_2-k_3)t}}{k_3 - k_2}\right) + C \\]

Dividing by \\(\mu = e^{k_3 t}\\):

\\[ \[\text{D}_2\text{H}^+\](t) = \frac{k_1 k_2\[\text{H}_3^+\]_0}{k_2 - k_1}\left(\frac{e^{-k_1 t}}{k_3 - k_1} - \frac{e^{-k_2 t}}{k_3 - k_2}\right) + Ce^{-k_3 t} \\]

Applying the boundary condition \\(\[\text{D}_2\text{H}^+\] = 0\\) at \\(t=0\\):

\\[ C = -\frac{k_1 k_2\[\text{H}_3^+\]_0}{k_2 - k_1}\left(\frac{1}{k_3 - k_1} - \frac{1}{k_3 - k_2}\right) \\]

Substituting back and collecting terms:

\\[ \boxed{\[\text{D}_2\text{H}^+\](t) = \frac{k_1 k_2\[\text{H}_3^+\]_0}{k_2 - k_1}\left(\frac{e^{-k_1 t} - e^{-k_3 t}}{k_3 - k_1} - \frac{e^{-k_2 t} - e^{-k_3 t}}{k_3 - k_2}\right)} \\]

Note that if any two of \\(k_1\\), \\(k_2\\), \\(k_3\\) are equal, an alternate form must be derived analogously to the \\(k_1 = k_2\\) case above.

## Solving for [D\\(_3^+\\)]

This result follows directly from conservation of mass. The total number of ions in the trap is constant:

\\[ \[\text{H}_3^+\](t) + \[\text{H}_2\text{D}^+\](t) + \[\text{D}_2\text{H}^+\](t) + \[\text{D}_3^+\](t) = \[\text{H}_3^+\]_0 \\]

Therefore:

\\[ \boxed{\[\text{D}_3^+\](t) = \[\text{H}_3^+\]_0 - \[\text{H}_3^+\](t) - \[\text{H}_2\text{D}^+\](t) - \[\text{D}_2\text{H}^+\](t)} \\]

where the expressions for the other three species are given by the boxed equations above.
