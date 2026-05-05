# review_lab_packet_tracer2
# Router Basic Configuration Lab (Packet Tracer)

## 📌 Overview

This lab demonstrates basic configuration tasks on two routers using Cisco Packet Tracer. The goal is to practice setting hostnames, securing access with passwords, and understanding password encryption.

---

## 🛠️ Lab Tasks

### 1. Connect Routers

* Connect **R1** and **R2** using:

  * `GigabitEthernet0/0` on R1 ↔ `GigabitEthernet0/0` on R2

---

### 2. Configure Hostnames

```bash
Router> enable
Router# configure terminal
Router(config)# hostname R1
```

Repeat on the second router:

```bash
Router(config)# hostname R2
```

---

### 3. Set Enable Password

```bash
R1(config)# enable password cisco
```

---

### 4. Set Enable Secret

```bash
R1(config)# enable secret ccna
```

---

### 5. Test Privileged Mode Access

* Exit to user exec mode:

```bash
R1(config)# end
R1#
R1# disable
R1>
```

* Try entering privileged mode:

```bash
R1> enable
```

✅ **Result:**
You must use the **enable secret password (`ccna`)**, because it overrides the enable password.

---

### 6. View Running Configuration

```bash
R1# show running-config
```

🔍 **Observation:**

* `enable password` appears in plain text
* `enable secret` is **encrypted**

---

### 7. Enable Password Encryption

```bash
R1(config)# service password-encryption
```

* Check configuration again:

```bash
R1# show running-config
```

🔐 **Result:**

* The `enable password` is now encrypted
* All plain-text passwords are converted to encrypted format

---

### 8. Save Configuration & Reload

```bash
R1# copy running-config startup-config
R1# reload
```

✅ After reload:

* Configuration is preserved
* Passwords and hostname remain unchanged

---

## 📚 Key Concepts Learned

* Difference between `enable password` and `enable secret`
* Password encryption using `service password-encryption`
* Saving configuration using `copy running-config startup-config`
* Basic router setup in Cisco IOS

---

## 🧠 Notes

* Always prefer `enable secret` over `enable password` for better security
* Encryption applied by `service password-encryption` is not highly secure, but better than plain text

---

## 📁 Tools Used

* Cisco Packet Tracer

---

## 🚀 Author

Created as part of CCNA practice labs
