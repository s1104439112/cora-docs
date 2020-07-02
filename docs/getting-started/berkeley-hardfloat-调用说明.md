
# Berkeley Hard-Float 调用说明

---

4 types of berkeley hardfloat are commonly used in cora, **multiply-and-addition, division, recfN2IEEE, and IEEE2recfN**.

**multiply-and-additions and divisions** are often integrated in **xmac**, for example, in KF module this is called as **kmac**, in TPG module this is called as **tmac** and in FC module this is called as **fmac**. The naming tradition is from **DLA**, in DLA, the main computational part is **mac**.

**IEEE2recfN** and **recfN2IEEE** are integrated in two parts, ping-pong registers and DMAs. Since the maximum data length is 32 bits, however, if we would like to send some information in recoded format directly, let's say, 33 bits in recoded format, it has to transfer twice. So, IEEE2recfN and recfN2IEEE were integrated in ping-pong registers, and what's more important, is that we can directly send IEEE format from CSB to registers. In DMAs, data were transfromed between recfn and IEEE(IEEE2recfn in RDMA and recfn2IEEE in WDMA).


## Multiply and Addition

This is 





















