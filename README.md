# DPU_Outputs

Files for using DPU on KV260 Vision AI Starter Kit

### Naming

`C1 -> 1 core`
`B4096 -> 4096 architecture`

---

### Load DPU Configuration on Board

If git was not installed with rootfs, install git

```
sudo dnf install -y git
```

Clone the repository in board

```
git clone https://github.com/kayracoskun/DPU_Outputs.git
```

Create app that will be loaded to the firmware

```
mkdir myApp

cd DPU_Outputs

cp OUT_C1_B4096/KV260.dtbo OUT_C1_B4096/shell.json OUT_C1_B4096/top_wrapper.bit.bin myApp

sudo mv myApp/ /lib/firmware/xilinx/
```

Load DPU app

```
sudo xmutil listapps

sudo xmutil unloadapp

sudo xmutil loadapp myApp
```

Check the DPU

```
sudo xdputil query

sudo show_dpu 
```
