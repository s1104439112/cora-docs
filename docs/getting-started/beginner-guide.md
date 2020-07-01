# <img class="dcr-icon" src="/img/dcr-icons/Flag.svg" /> Beginner's Guide

---

## Welcome To Cora

Cora an extended accelerator of NVDLA, focusing on the **non-AI** part of the algorithms in self-driving cars, such as control, localizations and trajectory generations.


## Naming of the General Modules

| Module      | Description |
| ----------- | ----------- |
| FC       | [frent/cartesian converter](https://blog.csdn.net/davidhopper/article/details/79162385)|
| GAS      | [Gather-Assemble-Scatter](https://conferences.computer.org/isca/pdfs/ISCA2020-4QlDegUf3fKiwUXfV0KdCm/466100a419/466100a419.pdf)(For Graph Computing)   |
| KF   | Kalman Filter |
| CORDIC | Using [cordic](https://zipcpu.com/dsp/2017/08/30/cordic.html) to transform x-y to r-theta, and to transform r-theta to x-y.|
| *MAC   | A collection of floating point calculator, to calculate **multiply-and-add**, and **division**. |
| *SC   | A collection of **sequence controllers** |
| *SC_DL   | The **data line** under the hierachy of sequence controller. |
| *SC_SG   | The **sequence generator** under the hierachy of sequence controller. |
| *RDMA   | DMA for read, all the discrete processors read raw datas from rdma.|
| *WDMA   | DMA for write, all the discrete processors write raw datas to wdma.|
| *RDMA_eg   | **Egress** of RDMA.|
| *RDMA_ig   | **Ingress** of RDMA.|
| *WDMA_cmd   | WDMA **command**|
| *WDMA_data   | WDMA **data**|
| PID   | PID control.|
| TPG  | Trajectory polynomial generation, corresponding to [spline](https://www.cnblogs.com/xpvincent/archive/2013/01/26/2878092.html).

## Basic Design Flows

This is the basic agile design flows of NProcessor team. **Agile** means largely rely on **design&reuse, mature flows, and effective communications(documentations)**. 

The displayed image is small, you might need to zoom in to see the details. 


<img class="agile design flows" src="/img/cora-svgs/basic-flows.svg" /> 

The whole framework is a combination of chipyard(riscv and other IPs, firesim, hammer), soDLA&cora, cocotb, BAG(berkeley analog generator), OpenRoad-flow(modified version of yosys, openroad, klayout) and published pdk(asap7nm, freepdk45nm, skywater130nm).

Verication process can be replaced by verilator and cocotb, upon requirements. **Since no direct verification tool support on chisel, formal verification process is optional.**


## Working Repositories

---

**cora**
cora development and testing in chisel3. 

**soDLA**
soDLA development and testing in chisel3. 

**npc_cocotb**
cora and soDLA testing under verilog

**firesim**
to be setup.

**hammer and openroad**
under virtual machines.

**BAG**
to be setup.



## Contacting with Our Team Members

If you have questions, here is the quickiest way to contact developers from our team or our 'brotherhood' team. But **when consulting to people from other team, please don't disclose the private part of our project**.  

**nprocessor team**

画面(githubid: redpanda3 qq: 2874626504 wechat: xiezuoyedexiaohao): 

cora, soDLA, hammer and openroad

薛辉(githubid: bg193):

cora(DMA part), soDLA, cocotb, verilator

小黑:

soDLA, chisel related

咧威：

cora, chisel related

小周:

cora(fc conversion), fpga related

jj:

soDLA test, cora test

夫子(KonPed, qq:415758192, icfb123456@163.com):

VLSI backend

**中科大计算科学所**

小李（github:CristinaZN）:

soDLA on firesim












