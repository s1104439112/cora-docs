
# Register Table For CSB

---

[Configuration Space Bus](http://nvdla.org/hw/v1/hwarch.html#external-interfaces)(CSB) is used as a control bus in NVDLA system, and it is also used in CORA system.

Before you define a register value. remember to check the address is not overlapped. 

In the current phase, the address is assigned **randomly**, no need to check.

## PID Table

|       | Address  |  data0  |   bits  |  data1 | bits    |
| ----- | -------  |  -----  |  -----  | -------| ------- |
| #pid op enable   |          |         |         |        |         |
| cora_pid_op_enable_0_wren  | h08 | cora_pid_op_enable | [0] |  |  |
| #pid rdma   |          |         |         |        |         |
| cora_pid_src_base_addr_high_0_wren  | h0c | cora_pid_src_base_addr_high | [31, 0] |  |  |
| cora_pid_src_base_addr_low_0_wren  | h10 | cora_pid_src_base_addr_low | [31, 0] |  |  |
| #pid core   |          |         |         |        |         |
| cora_pid_misc_cfg_0_wren  | h0c | detectTininess | [8] | roundingMode | [2, 0] |
| cora_pid_max_n_0_wren  | h10 | max_n | [31, 0] |  |  |

## KF Table

|       | Address  |  data0  |   bits  |  data1 | bits    |
| ----- | -------  |  -----  |  -----  | -------| ------- |
| #kf op enable   |          |         |         |        |         |
| cora_kf_op_enable_0_wren  | hc08 | cora_kf_op_enable | [0] |  |  |
| #rdma   |          |         |         |        |         |
| TBD  |             |         |         |        |         |
| #kf core   |          |         |         |        |         |
| cora_kf_mat_h_00_hardfloat_wren  | hc10 | cora_kf_mat_h_00_hardfloat | [31, 0] |  |
| cora_kf_mat_h_01_hardfloat_wren  | hc11 | cora_kf_mat_h_01_hardfloat | [31, 0] |  |
| cora_kf_mat_h_02_hardfloat_wren  | hc12 | cora_kf_mat_h_02_hardfloat | [31, 0] |  |
| cora_kf_mat_h_03_hardfloat_wren  | hc13 | cora_kf_mat_h_03_hardfloat | [31, 0] |  |
|      |          |         |         |        |         |
| cora_kf_mat_h_10_hardfloat_wren  | hc14 | cora_kf_mat_h_10_hardfloat | [31, 0] |  |
| cora_kf_mat_h_11_hardfloat_wren  | hc15 | cora_kf_mat_h_11_hardfloat | [31, 0] |  |
| cora_kf_mat_h_12_hardfloat_wren  | hc16 | cora_kf_mat_h_12_hardfloat | [31, 0] |  |
| cora_kf_mat_h_13_hardfloat_wren  | hc17 | cora_kf_mat_h_13_hardfloat | [31, 0] |  |
|      |          |         |         |        |         |
| cora_kf_mat_h_20_hardfloat_wren  | hc18 | cora_kf_mat_h_20_hardfloat | [31, 0] |  |
| cora_kf_mat_h_21_hardfloat_wren  | hc19 | cora_kf_mat_h_21_hardfloat | [31, 0] |  |
| cora_kf_mat_h_22_hardfloat_wren  | hc1a | cora_kf_mat_h_22_hardfloat | [31, 0] |  |
| cora_kf_mat_h_23_hardfloat_wren  | hc1b | cora_kf_mat_h_23_hardfloat | [31, 0] |  |
|      |          |         |         |        |         |
| cora_kf_mat_h_30_hardfloat_wren  | hc1c | cora_kf_mat_h_30_hardfloat | [31, 0] |  |
| cora_kf_mat_h_31_hardfloat_wren  | hc1d | cora_kf_mat_h_31_hardfloat | [31, 0] |  |
| cora_kf_mat_h_32_hardfloat_wren  | hc1e | cora_kf_mat_h_32_hardfloat | [31, 0] |  |
| cora_kf_mat_h_33_hardfloat_wren  | hc1f | cora_kf_mat_h_33_hardfloat | [31, 0] |  |
|      |          |         |         |        |         |
| cora_kf_mat_r_00_hardfloat_wren  | hc30 | cora_kf_mat_r_00_hardfloat | [31, 0] |  |
| cora_kf_mat_r_01_hardfloat_wren  | hc31 | cora_kf_mat_r_01_hardfloat | [31, 0] |  |
| cora_kf_mat_r_02_hardfloat_wren  | hc32 | cora_kf_mat_r_02_hardfloat | [31, 0] |  |
| cora_kf_mat_r_03_hardfloat_wren  | hc33 | cora_kf_mat_r_03_hardfloat | [31, 0] |  |
|      |          |         |         |        |         |
| cora_kf_mat_r_10_hardfloat_wren  | hc34 | cora_kf_mat_r_10_hardfloat | [31, 0] |  |
| cora_kf_mat_r_11_hardfloat_wren  | hc35 | cora_kf_mat_r_11_hardfloat | [31, 0] |  |
| cora_kf_mat_r_12_hardfloat_wren  | hc36 | cora_kf_mat_r_12_hardfloat | [31, 0] |  |
| cora_kf_mat_r_13_hardfloat_wren  | hc37 | cora_kf_mat_r_13_hardfloat | [31, 0] |  |
|      |          |         |         |        |         |
| cora_kf_mat_r_20_hardfloat_wren  | hc38 | cora_kf_mat_r_20_hardfloat | [31, 0] |  |
| cora_kf_mat_r_21_hardfloat_wren  | hc39 | cora_kf_mat_r_21_hardfloat | [31, 0] |  |
| cora_kf_mat_r_22_hardfloat_wren  | hc3a | cora_kf_mat_r_22_hardfloat | [31, 0] |  |
| cora_kf_mat_r_23_hardfloat_wren  | hc3b | cora_kf_mat_r_23_hardfloat | [31, 0] |  |
|      |          |         |         |        |         |
| cora_kf_mat_r_30_hardfloat_wren  | hc3c | cora_kf_mat_r_30_hardfloat | [31, 0] |  |
| cora_kf_mat_r_31_hardfloat_wren  | hc3d | cora_kf_mat_r_31_hardfloat | [31, 0] |  |
| cora_kf_mat_r_32_hardfloat_wren  | hc3e | cora_kf_mat_r_32_hardfloat | [31, 0] |  |
| cora_kf_mat_r_33_hardfloat_wren  | hc3f | cora_kf_mat_r_33_hardfloat | [31, 0] |  |
| #kf cordic   |          |         |         |        |         |
| cora_kf_misc_cfg_0_wren  | hc0c | detectTininess | [13] | roundingMode | [2, 0] |
| #kf kmac   |          |         |         |        |         |
| cora_kf_misc_cfg_0_wren  | hc0c | detectTininess | [13] | roundingMode | [2, 0] |


## TPG Table


|       | Address  |  data0  |   bits  |  data1 | bits    |
| ----- | -------  |  -----  |  -----  | -------| ------- |
| #tpg op enable   |          |         |         |        |         |
| cora_tdma_op_enable_0_wren  | hd808 | cora_tdma_op_enable | [0] |  |  |
| #rdma   |          |         |         |        |         |
| cora_tdma_datain_addr_high_0_wren  | hd80c | datain_addr_high_0 | [31, 0] |  |  |
| cora_tdma_datain_addr_low_0_wren  | hd810 | datain_addr_low_0 | [31, 0] |  |  |
| cora_tdma_datain_addr_num_0_wren | hd814 |  datain_num | [31, 0] | | |
| #tmac   |          |         |         |        |         |
| cora_kf_misc_cfg_0_wren  | hc0c | detectTininess | [13] | roundingMode | [2, 0] |




















