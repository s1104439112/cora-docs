

# Retiming Guide

---

Each of the xmac and xcordics are computational intensive modules, to avoid the timing issue, input and output retiming are equipped on them.

The delay of one computational unit is given by 

\begin{equation}
rt_{in} + delay + rt_{out}
\end{equation}

For example, the delay of multiply-and-add pipe is 

\begin{equation}
2 + 2 + 2
\end{equation}

The delay of the division pipe is 

\begin{equation}
2 + 24 + 2
\end{equation}

quote "aswaterman commented on Dec 27, 2017
It's too dependent on your application for me to provide an answer. The first option has latency of 25-ish cycles and throughput of 1/3 operations per cycle, but the area cost is high and the clock rate might be limited. The second option has latency of S-ish cycles (where S is the width of the significand) and has throughput of 1/S operations per cycle, but the area cost is low and it can run at higher clock rate."

So, the division delay is sigwidth, which is 24(need to be tested). The rt_in and rt_out should be adjusted by the real timing results(by VLSI flow).



