
# Applying Berkeley Hard-Float 

---

4 types of berkeley hardfloat are commonly used in cora, **multiply-and-add, division, recfN2IEEE, and IEEE2recfN**.

**multiply-and-add and divide** are often integrated in **xmac**, for example, in KF module this is called as **kmac**, in TPG module this is called as **tmac** and in FC module this is called as **fmac**. The naming tradition is from **DLA**, in DLA, the main computational part is **mac**.

**IEEE2recfN** and **recfN2IEEE** are integrated in two parts, ping-pong registers and DMAs. Since the maximum data length is 32 bits, however, if we would like to send some information in recoded format directly, let's say, 33 bits in recoded format, it has to transfer twice. So, IEEE2recfN and recfN2IEEE were integrated in ping-pong registers, and what's more important, is that we can directly send IEEE format from CSB to registers. In DMAs, data were transfromed between recfn and IEEE(IEEE2recfn in RDMA and recfn2IEEE in WDMA).


## Multiply and Add

This can be found under **xmac**

```
// First, initialize

val u_mac = Module(new MulAddRecFNPipe(expWidth = 8, sigWidth = 24, latency = 2))

//latency需要小于等于2，也就是至少在2个周期后，输出结果。

```

### I/O information

```
val validin = Bool(INPUT)
val op = Bits(INPUT, 2)
val a = Bits(INPUT, expWidth + sigWidth + 1)
val b = Bits(INPUT, expWidth + sigWidth + 1)
val c = Bits(INPUT, expWidth + sigWidth + 1)
val roundingMode   = UInt(INPUT, 3)
val detectTininess = UInt(INPUT, 1)
val out = Bits(OUTPUT, expWidth + sigWidth + 1)
val exceptionFlags = Bits(OUTPUT, 5)
val validout = Bool(OUTPUT)

```

op is default to zero, roundingMode and detectTiness are given by **ping-pong reg**, exceptionFlags transfer to the sequential generator under the sequential controller and to the **ping-pong reg**, if exception happpens, the sequential generator jumps to done/idle state, the exception type should return a type information to **ping-pong reg**, thus transfered by CSB to programming interface.

a, b and c are the input, performing a*b+c operation.


### multiplication operation alone

According to the [testing-file](https://github.com/ucb-bar/berkeley-hardfloat/blob/2f9cdc3b0e701b644b2ebb860ef2485b05b7d605/src/main/scala/ValExec_MulAddRecFN.scala), 

```
mulAddRecFN.io.a := recFNFromFN(expWidth, sigWidth, io.a)
mulAddRecFN.io.b := recFNFromFN(expWidth, sigWidth, io.b)
mulAddRecFN.io.c :=
    ((io.a ^ io.b) & UInt(BigInt(1)<<(expWidth + sigWidth - 1)))<<1
```

c is not zero, c should be ((io.a ^ io.b) & UInt(BigInt(1)<<(expWidth + sigWidth - 1)))<<1, because we have to exclude overflow or underflow conditions.

Remember, this is just a basic form, don't put too much time into detailed **why**.


### addition operation alone

According to the [testing-file](https://github.com/ucb-bar/berkeley-hardfloat/blob/2f9cdc3b0e701b644b2ebb860ef2485b05b7d605/src/main/scala/ValExec_MulAddRecFN.scala), 

```
mulAddRecFN.io.a := recFNFromFN(expWidth, sigWidth, io.a)
mulAddRecFN.io.b := UInt(BigInt(1)<<(expWidth + sigWidth - 1))
mulAddRecFN.io.c := recFNFromFN(expWidth, sigWidth, io.b)

```

b is the recoded form of one, a*1+c=a+c.


## Divide

According to the [testing-file](https://github.com/ucb-bar/berkeley-hardfloat/blob/2f9cdc3b0e701b644b2ebb860ef2485b05b7d605/src/main/scala/ValExec_DivSqrtRecFN_small.scala), 

under division condition, 

```
ds.io.sqrtOp := Bool(false)
```

uder sqrt condition,

```
ds.io.sqrtOp := Bool(true)
```


## recfn/ieee Conversion

These are **combinational** circuits. Using 'recFNFromFN' and 'fNFromRecFN'.


























