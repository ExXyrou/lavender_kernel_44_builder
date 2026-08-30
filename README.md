# 🛠️ Xiaomi Redmi Note 7 (Lavender) Kernel Build Workflows

Automated GitHub Actions workflows to compile custom kernels for **Xiaomi Redmi Note 7 (Lavender)** using **AnyKernel3** flashable zip packages and automated **Telegram notifications**.

---

## 1. 🛠️ Predator Stormbreaker Kernel 4.4 (`PS_KERNEL_44_BUILD.yml`)

A streamlined workflow designed to compile the Predator Stormbreaker Kernel variant using AOSP Clang.

### Features & Inputs
* **`LOCALVERSION`**: Custom kernel name suffix (e.g., `MyKernel-v1.0`).
* **`VERSION_SUFFIX`**: Choose additional suffix mode (`none`, `localversion_auto`, or `build-date`).
* **`DEFAULT_HOSTNAME` / `BUILD_USER` / `BUILD_HOST`**: Custom compiler host and user identification settings.
* **`BUILD_NEWCAM`**: Toggle between `newcam` and `oldcam` build types.
* **`INJECT_KSU`**: Optional **KernelSU** integration (`true`/`false`).

---

## 2. 🛠️ San Kernel 4.4 (`SAN_KERNEL_44_BUILD.yml`)

A feature-rich workflow for compiling San Kernel with support for multiple branches, advanced compression (`.xz`), and haptics control.

### Features & Inputs
* **`KERNEL_BRANCH`**: Select the target source branch (`PLTS`, `st74`, or `st78`).
* **`DISPLAY_BRANCH_NAME`**: Toggle whether to append the branch name to the final kernel string.
* **`LOCALVERSION`**: Custom kernel name string.
* **`VERSION_SUFFIX`**: Choose version naming suffix (`none`, `localversion_auto`, or `build-date`).
* **`QTI_HAPTICS`**: Include or exclude QTI Haptics support.
* **`BUILD_NEWCAM`**: Toggle camera blob configurations.
* **`INJECT_KSU`**: Optional **KernelSU** injection (`true`/`false`).

---

## ⚙️ Required Repository Secrets

To ensure build notifications and zip file delivery work properly via Telegram, make sure to add the following secrets in your GitHub Repository settings (`Settings > Secrets and variables > Actions`):

* `BOT_API`: Your Telegram Bot Token.
* `CHAT_ID`: Your Telegram Chat ID or Channel ID.

---

## 🚀 How to Run
1. Go to the **Actions** tab in your GitHub repository.
2. Select either **🛠️ PREDATOR STORMBREAKER KERNEL 4.4** or **🛠️ SAN KERNEL 4.4** from the left sidebar.
3. Click **Run workflow**, adjust your preferred inputs, and click **Run workflow** again to start building.
