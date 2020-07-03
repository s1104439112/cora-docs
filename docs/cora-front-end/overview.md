
# Overview

---

The [front-end](https://github.com/coraproject/cora) is developed under chisel, using the similar chisel flow of [soDLA](https://github.com/soDLA-publishment/soDLA). 



## File Structures
```
├─spec: specifications
├─apb2csb: apb2csb conversion
├─berkeley-hardfloat: berkeley hardfloat for calculations
├─rocket/fpu: wrapped-up module of berkeley-hardfloat, allowing you to utilize hardfloat in chisel3
├─nocif: external intefaces of DMA group
├─ofdm
|  ├─cordic: cordic modules for rectangular/polar conversions
|  └ syncrom: rom for each of the iterative cordic stages
├─slibs: includes some libraries from soDLA
|   ├─cora_fifo: inherited from fifo generators from soDLA
|   ├─bc/is_pipe: inherited from pipes from soDLA
|   ├─cora_csb_logic: transactions of csb to register 
|   ├─cora_basic_reg_single: common single register appears in [ping-pong reg](http://nvdla.org/hw/v1/hwarch.html)
|   └CORA/NV_gate_power & slcg: power gating
|
|
└cora
    ├─pid
    |   ├─rdma
    |   ├─wdma
    |   ├─sc&pe: sequential control + process engine, pe includes one mac
    |   └reg
    |   
    ├─gas
    |   ├─rdma
    |   ├─wdma
    |   ├─sc&pe: sequential control + process engine, pe includes one mac
    |   └reg
    |  
    ├─kf
    |   ├─cordic
    |   ├─kmac: 4mac + 1div
    |   ├─kdma
    |   ├─kpsc: prediction sequential control
    |   └ kusc: update sequential control
    └tpg
        ├─spline: sequential control
        ├─tbuf: a groups of buffer, to store intermediate variables
        ├─tdma: dma to store input to tbuf
        └ tmac: 4mac + 4div
```


## Implicit Configurations

Below is the ring structure of implicit configurations(coraConfig)

```
cora full(under spec folder) -> project_soec(under spec folder) 
-> pid config -> kf config -> tpg config -> gas config // under each of the folders
-> coraConfig(under spec folder)

```
























