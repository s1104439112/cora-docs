
# Applying ofdm cordic(need to be tested)

Cordic is a common algorithm in performing r-theta/cos-sin transform. [This type of cordic](https://github.com/grebe/ofdm/blob/master/src/main/scala/ofdm/CORDIC.scala) is used in cora project. 

This will generate a setup of ROM. Two types of Iterative cordic, circularVectoring to calculate the rectangular to polar, and circularRotation to calculate to polar to rectangular(cos, and sin result).

We packed them together into *xcordic*, with modified INT2RecFN converter.

## reg2polar

Need to turn mode = 0, the input is x&y, and the output is mag&theta. 


## polar2reg

Need to turn mode = 1, the input is mag&theta, and the output is cos&sin.
























