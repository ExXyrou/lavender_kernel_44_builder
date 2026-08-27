# 🛠️ Lavender Kernel Build Hub

Welcome to the automated CI/CD build system for **Xiaomi Redmi Note 7 (lavender)** kernels! This repository utilizes GitHub Actions to compile custom Linux kernels smoothly, automatically package them into flashable zip files via AnyKernel3, and send real-time status updates straight to Telegram.

---

## 🚀 Available Workflows

We currently maintain two primary custom kernel build workflows, each utilizing specialized toolchains, configurations, and features tailored for the best user experience.

### 1. Predator Strombreaker Kernel (`4.4`)
* **Source Repository:** `predator_strombreaker_kernel` (Branch: `oldcam`)
* **Toolchain:** AOSP Clang (`r383902`)
* **Compression Format:** GZIP (`Image.gz` / `Image.gz-dtb`)
* **Overview:** A finely-tuned performance kernel built for stability and everyday multitasking responsiveness on Lavender.

### 2. San Kernel (`4.4`)
* **Source Repository:** `san_kernel` (Branch: `oldcam`)
* **Toolchain:** ZyC Clang (`15.0.7`)
* **Compression Format:** XZ (`Image.xz` / `Image.xz-dtb`)
* **Overview:** Features advanced power-efficient and gaming configurations, complete with optional **QTI Haptics** support for enhanced tactile feedback.

---

## ⚙️ Workflow Inputs & Configuration

Both workflows share flexible `workflow_dispatch` triggers, allowing you to customize the build right from the GitHub Actions tab:

| Input Parameter | Type | Default | Description |
| :--- | :---: | :---: | :--- |
| `LOCALVERSION` | String | *None* | Custom suffix name for your kernel (e.g., `-MyCustomKernel-v1.0`). |
| `LOCALVERSION_AUTO` | Boolean | `false` | Automatically appends local version control indicators if enabled. |
| `DEFAULT_HOSTNAME` | String | *Required* | Network hostname assigned inside the kernel (e.g., `xiaomi@redmi`). |
| `BUILD_USER` | String | *Required* | The username displayed in kernel compilation details (e.g., `xiaomi`). |
| `BUILD_HOST` | String | *Required* | The hostname displayed during compilation (e.g., `redmi`). |
| `QTI_HAPTICS` *(San Only)* | Boolean | `false` | Toggles specialized QTI haptics support driver compilation. |
| `APPLY_TWEAKS` | Boolean | `false` | Injects optimized performance, battery, and gaming tweaks (such as custom CPU governors, I/O schedulers, and BBR congestion control). |
| `INJECT_KSU` | Boolean | `false` | Seamlessly integrates **KernelSU** into the source before compilation. |

---

## 📦 Features & Highlights

* **⚡ Ccache Integration:** Caches previously compiled object files to drastically reduce subsequent build times.
* **🦊 KernelSU Ready:** Built-in option to automatically fetch and patch the latest KernelSU framework sources.
* **🚀 Smart Tweaks:** One-click application of advanced CPU boosting, custom I/O schedulers (`Kyber`/`BFQ`), and network optimizations (`BBR`).
* **🤖 Telegram Bot Notifications:** Automatically sends an alert when a build starts, and attaches either the flashable zip on **Success** or the error log (`build.log`) on **Failure**.

---

## 🚀 How to Trigger a Build

1. Navigate to the **Actions** tab in your GitHub repository.
2. Select either **🛠️ PREDATOR STROMBREAKER KERNEL 4.4 BUILD** or **🛠️ SAN KERNEL 4.4 BUILD** from the left sidebar.
3. Click the **Run workflow** dropdown button.
4. Fill in your desired configuration inputs (custom name, tweaks, KernelSU injection, etc.) and click **Run workflow**.
5. Wait for the process to finish, and grab your zip file directly from your connected Telegram chat!
