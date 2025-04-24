# Embedded_Bond
![Pic](https://github.com/user-attachments/assets/6bb3168d-5271-472b-8906-8f2ca6571c2b)

A Pricing Sheet to calculate price of bonds with Embedded options.
A Bond with embedded options is a vanilla bond stapled with an option clause,
Call being the ability to buy at a later date at the Strike,
and Put being the ability to sell at a later date at the Strike.

However in the case of a bond, A callable bond has the clause of being bought back by the issurer and a puttable bond can be sold back to the issurer
An Embedded Bond is priced simply as,
```math
{Embedded Bond Price} = {Base Bond Price} &plusmn; {Option Value}
```
where, it is added for a put option and subtracted for a call.

![image](https://github.com/user-attachments/assets/6dcf53e6-ad53-42a8-8808-5ca78375dffe)

The Valuation of Option on the recombing Binomial Model for American Options.
American options differ from European ones in the sense of Excercie timming, where a european option can only be excercised at only the specified date, an american call can be excercised anytime before the maturity.

Hence, the valuation schema changes as the valuation is done at every single node in the tree.
Value at node,
```math
\text{Value at node} = \max(\text{Current Payoff}, \text{Expected Present Value of future Payoffs})
```
where,
```math
\text{Expected Present Value of future Payoffs} = e^{-r{\Delta}t}\times[q\times{upmove}\times{Payoff_{1}} + (1-q)\times{downmove}\times{Payoff_{2}}]
```
q = risk neutral probability of an upmove
```math
q = \frac{e^{r} - d}{u - d} ; u > e^r > d
```
---
An Important Note is that it is considered suboptimal to excercise a call option before it's excercise time, this is due to the fact Theta has a positive relationship with call options and increasing time will lead to the highest Value. Hence, an American Call Option is valued the same way as an European Call Option.

The Payoff is calculated differently for call and put,

For Call,
```math
{Payoff} = \max(S_{t} - K, 0)
```
For Put,
```math
{Payoff} = \max(K - S_{t}, 0)
```
where,

$S_{t}$ is the underlying asset

K is the Stike Price
