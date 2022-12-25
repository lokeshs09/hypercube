# Tailored Staking Yield

## Token Dilution

As previously defined, we can look at the predicted Staked Dilution (i.e. Tailored Staking Yield) and Un-staked Dilution. The change in fractional representation (i.e. ownership) of a set of tokens inside a bigger set is characterized as dilution in this context. In this meaning, dilution can be a positive or negative value: an increase in fractional ownership (staked dilution / Tailored Staking Yield) or a decrease in fractional ownership (staked dilution / Tailored Staking Yield) (un-staked dilution).

As the general token pool grows with inflation supply, we're interested in the relative change in ownership of staked vs un-staked tokens. As previously stated, only staked token holders would receive this issuance, raising the staked token fractional representation of the Current Supply Cap.

Using the same Supply Time Table parameters as before, the fraction of staked supply grows as indicated in the graph below.

**Growth of Staked Supply**

![Figure4](https://i.imgur.com/zjs5YmQ.png)

Due to this relative change in representation, the proportion of stake of any token holder will also change as a function of the Inflation Schedule and the proportion of all tokens that are staked.

Of initial interest, however, is the dilution of un-staked tokens, or ![f1]. In the case of un-staked tokens, token dilution is only a function of the Inflation Schedule because the amount of un-staked tokens doesn't change over time.

This can be seen by explicitly calculating un-staked dilution as ![f1]. The un-staked proportion of the token pool at time ![f2] is ![f3] and ![f4] is the incremental inflation rate applied between any two consecutive time points.  ![f5] and ![f6] is the amount of un-staked and total XPZ on the network, respectively, at time ![f7]. Therefore ![f8]. 


![f10]

![f11]

However, because inflation issuance only increases the total amount and the un-staked supply doesn't change:


![f12]

![f13]

So  ![f1] becomes:


![f14]

![f15]

Or generally, dilution for un-staked tokens over any time frame undergoing inflation ![f16] :

![f17]

So as guessed, this dilution is independent of the total proportion of staked tokens and only depends on inflation rate. This can be seen with our example Supply Time Table here:

![f18]

 
[f1]: http://chart.apis.google.com/chart?cht=tx&chl=D_{us}
[f2]: http://chart.apis.google.com/chart?cht=tx&chl=t
[f3]: http://chart.apis.google.com/chart?cht=tx&chl=P_{us}(t_{N})
[f4]: http://chart.apis.google.com/chart?cht=tx&chl=I_{t}
[f5]: http://chart.apis.google.com/chart?cht=tx&chl=XPZ_{us}(t)
[f6]: http://chart.apis.google.com/chart?cht=tx&chl=XPZ_{totoal}(t)
[f7]: http://chart.apis.google.com/chart?cht=tx&chl=t
[f8]: http://chart.apis.google.com/chart?cht=tx&chl=P_{us}(t)=XPZ_{us}(t)/XPZ_{total}(t)
[f9]: https://chart.apis.google.com/chart?cht=tx&chl=F=G\frac{(m_1m_2)}{r^2}
[f10]: https://chart.apis.google.com/chart?cht=tx&chl=D_{us}=(\frac{P_{us}(t_1)-P_{us}(t_0)}{P_{us}(t_0)})
[f11]: https://chart.apis.google.com/chart?cht=tx&chl=D_{us}=\frac{\frac{XPZ_{us}(t_2)}{XPZ_{total}(t_2)}-\frac{XPZ_{us}(t_1)}{XPZ_{us}(t_1)}}{\frac{XPZ_{us}(t_1)}{XPZ_{total}(t_1)}}
[f12]: https://chart.apis.google.com/chart?cht=tx&chl=XPZ_{us}(t_2)=XPZ_{us}(t_{1})
[f13]: https://chart.apis.google.com/chart?cht=tx&chl=XPZ_{total}(t_2)=XPZ_{total}(t_{1})\times(1%2BI_{t_1})
[f14]: https://chart.apis.google.com/chart?cht=tx&chl=D_{us}=\frac{\frac{XPZ_{us}(t_1)}{XPZ_{total}(t_1)\times(1%2BI_{i})}-\frac{XPZ_{us}(t_1)}{XPZ_{us}(t_1)}}{\frac{XPZ_{us}(t_1)}{XPZ_{total}(t_1)}}
[f15]: https://chart.apis.google.com/chart?cht=tx&chl=_D_{us}=\frac{1}{1%2BI_{i}}%2D1
[f16]: https://chart.apis.google.com/chart?cht=tx&chl=I
[f17]: https://chart.apis.google.com/chart?cht=tx&chl=D_{us}=%2D\frac{I}{I%2B1}

[f18]: https://i.imgur.com/BjriGrD.png