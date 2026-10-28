<div align="center">

# 🛡️ Cybersecurity-lab-setup-networkwalks-B084-week1

**Task Tag:** `networkwalks-B084-week1_Cybersecurity-Lab-Setup`  
**Author:** [Farhad Khan](https://www.linkedin.com/in/farhadmkhan/)

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📝 Executive Overview

This repository about creating a home `kali linux` Practice lab and setting up their installation process and network setting by changing the default `NAT` network setting into `NAT Network` which is `10.0.0.1/24` and we will do that process with other VM's. So they can easily interact with each other. 

So this is basically the project task from `NETWORKWALKS-INTERNSHIP-BATCH-B084` of week1 and this is my week1 day 3 completing before the due date.

---

## 🎯 Lab Objectives

* Installing the Softwear that allow us to use the VM's VM_box/VMware in our windows system 
* Then installing our main virtual machine kali linux and moving it into VM box.
* After that then Changing the default network setting of VM box .
* Checking the connection if its working or not. 
* Make sure the connection wroking smoothly then check the ip.

---

## ⚙️ Core Technical Specifications

| Parameter | Operational Environment Values |
| :--- | :--- |
| **Host System Architecture** | Windows 10 / Intel Core i7 / 8 GB RAM |
| **Hypervisor Software** | Oracle VirtualBox v7.2 |
| **Active Instance** | Kali Linux v2026.2 (Allocated: 2048 MB RAM) |
| **Network Type** | Custom NAT Network (`NatNetwork`) |
| **IP Allocation Scheme** | Static Allocation |
| **Subnet Mask / Block** | 10.0.0.0/24 |
| **Assigned Node IP** | 10.0.0.2 |
| **Default Gateway IP** | 10.0.0.1 |
| **Primary Domain Resolver** | 8.8.8.8 (Google Public DNS) |

---

## 🪜 Step-by-Step Practical Build

### Phase 1: Install 7-zip & Extract the kali linux 
<img width="527" height="54" alt="image" src="https://github.com/user-attachments/assets/6f10ddfe-d2a4-4113-bde4-0ef4a3a849df" />

---

### Phase 2: Moving kali linux files ISO,VDI into VM Box
<img width="523" height="79" alt="image" src="https://github.com/user-attachments/assets/ef8f4184-2e48-43bd-b0fa-833ff0484e5d" />


<img width="659" height="288" alt="image" src="https://github.com/user-attachments/assets/332a6641-febd-4ff5-8fde-29c07c69c8ac" />


Select the new button then import the VM file. VDI,ISO

<img width="700" height="408" alt="image" src="https://github.com/user-attachments/assets/1199a65d-99f1-42bb-8c24-f8bc8ba01899" />

visit to the file location and select it it will imported automatically just named it and click Finish.

---

### Phase 3: Configuring the Network
Click that tabs.

<img width="963" height="539" alt="image" src="https://github.com/user-attachments/assets/7d13d016-413b-4a12-ad5e-b8473058b79e" />

Then navigate to this and use the same settings and click apply.

<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/edc5efa3-b5d4-4e2b-9df4-7a91a7a2867a" />

```
```
### Phase 4: Working with kali linux 

Move there 

<img width="295" height="133" alt="image" src="https://github.com/user-attachments/assets/5571e17b-c823-4543-8686-37b1e8501d1f" />

Use the same settings.









<img width="702" height="552" alt="image" src="https://github.com/user-attachments/assets/c691d827-cc75-4c21-9762-544d551e1e21" />


---

## 🔎 Comprehensive Subnet Verification

To guarantee that the virtual networking stack behaves exactly as required, the interface metrics were probed directly from the terminal layer.

### Interface Property Examination
Running the interface identification tool confirmed that our primary network link has successfully obtained the designated internal routing address:

```bash
ip a show eth0
```

<img width="290" height="84" alt="image" src="https://github.com/user-attachments/assets/56a00639-e6fe-4e9e-a781-84d164b1ce7e" />


### Diagnostics Matrices

| Verification Test Vector | Terminal Command Executed | Expected Sandbox Outcome | Status |
| :--- | :--- | :--- | :--- |
| **Address Assessment** | `ip a` | Interface matches `10.0.0.2/24` precisely | ✅ Verified |
| **Gateway Reachability** | `ping -c 3 10.0.0.1` | Round-trip transmission with zero packet drop | ✅ Verified |
| **Outbound Wan Verification** | `ping -c 3 8.8.8.8` | ICMP traffic clears hypervisor translation layer | ✅ Verified |
| **DNS Resolution Validation** | `nslookup networkwalks.com` | Upstream resolvers answer with correct A-records | ✅ Verified |
| **Tool Inventory Audit** | `nmap --version` | Auditing bin files are present and mapped | ✅ Verified |
| **State Preservation Audit** | `VirtualBox Snapshot Tool` | System states can freeze and roll back on demand | ✅ Verified |

---

## 🛟 Resilience & Fault Tolerance Strategy

With the initial connection rules and static setups completed, a complete virtual disk snapshot was committed to the platform repository under the designation: `Clean Kali - Network Setup`.

This acts as our master restore checkpoint. Should heavy scanning scripts, raw system exploits, or breaking package configurations corrupt the kernel settings during future assessment labs, the node can be reset back to this specific verified operating baseline instantly.

