<div align="center">

# 🛠️ VIP Lavender Kernel Builder

### 🚀 Advanced Automated Custom Linux Kernel CI for Xiaomi Redmi Note 7 (`lavender`)
*Powered by GitHub Actions, AnyKernel3 & Custom Tweaks*

</div>

---

## 📖 About
**VIP Lavender Kernel Builder** is an upgraded, high-performance version of the standard kernel builder workflow. Built specifically for the **Xiaomi Redmi Note 7 (`lavender`)**, this VIP edition adds advanced options such as **pre-configured kernel sources (San & Predator)**, **KernelSU injection (`xxKSU`)**, and **custom performance profiles (EAS/HMP optimizations)**.

---

## 🔄 What's Different from the Standard Version?

| Feature / Setting | Standard Version | 🌟 VIP Version |
| :--- | :--- | :--- |
| **Kernel Sources** | Manual custom URL input only. | Adds quick selection options for **San** and **Predator-Strombreaker** (with auto-configured URLs and branches). |
| **KernelSU Integration** | Not available. | Built-in option to inject **xxKSU** automatically (`INJECT_KSU`). |
| **Performance Profiles** | Standard default compilation. | Custom tuning profiles (`none`, `eas`, `eas-extreme`, `hmp`, `hmp-extreme`) to adjust schedulers, tick rates (HZ), and debugging overhead. |
| **Toolchain Overrides** | Manual selection per run. | Automatically sets optimized toolchains for specific sources (e.g., Neutron for San, Clang r383902 for Predator). |

---

## ⚙️ Workflow Inputs & Parameters

When triggering this workflow manually via the **Actions** tab, you can configure the following:

| Parameter | Type | Required? | Description & Example |
| :--- | :--- | :---: | :--- |
| `KERNEL_SOURCE` | Choice | **Yes** | Select source: `custom`, `predator-strombreaker`, or `san` |
| `CUSTOM_KERNEL_URL` | String | Conditional | Custom repository URL (Required if `KERNEL_SOURCE` is set to `custom`) |
| `KERNEL_BRANCH` | Choice | **Yes** | Select branch (`custom` or `oldcam`) |
| `CUSTOM_KERNEL_BRANCH` | String | Conditional | Custom branch name (Required if branch is set to `custom`) |
| `KERNEL_DEFCONFIG` | String | **Yes** | Target defconfig name (e.g., `lavender_defconfig`) |
| `LOCALVERSION` | String | No | Custom kernel suffix name (e.g., `-VIP-v1.0`) |
| `DEFAULT_HOSTNAME` | String | **Yes** | Kernel hostname (e.g., `xiaomi@redmi`) |
| `BUILD_USER` | String | **Yes** | Build username (e.g., `xiaomi`) |
| `BUILD_HOST` | String | **Yes** | Build hostname (e.g., `redmi`) |
| `KERNEL_TWEAK` | Choice | **Yes** | Performance profile (`none`, `eas`, `eas-extreme`, `hmp`, `hmp-extreme`) |
| `INJECT_KSU` | Choice | **Yes** | KernelSU option (`none` or `xxKSU`) |
| `UBUNTU_VERSION` | Choice | **Yes** | Ubuntu runner version (`ubuntu-latest`, `ubuntu-24.04`, `ubuntu-22.04`, `ubuntu-20.04`) |
| `CLANG_SOURCE` | Choice | **Yes** | Clang toolchain source (`custom` or `neutron`) |
| `CUSTOM_CLANG_URL` | String | Conditional | Custom Clang download URL (Required if toolchain is `custom`) |

---

## 🚀 Key Features

*   **⚡ Built-in Performance Tweaks:** Easily switch between EAS and HMP schedulers, or activate *extreme* profiles (1000Hz, aggressive optimizations, and disabled debugging overhead).
*   **🦊 One-Click KernelSU:** Automatically clones and integrates **xxKSU** along with necessary filesystem configurations (`CONFIG_OVERLAY_FS`).
*   **🔗 Smart Presets:** Native support for popular community kernels like **San** and **Predator-Strombreaker** with automated configurations.
*   **📦 Ready-to-Flash ZIP:** Automatically wraps the compiled kernel image into a flashable ZIP using **AnyKernel3**.
*   **📢 Telegram & Release Integration:** Sends real-time notifications to Telegram and automatically publishes the resulting ZIP file to GitHub **Releases**.

---

## 💡 How to Use

1. Go to the **Actions** tab in your GitHub repository.
2. Select the **🛠️ VIP Lavender Kernel Builder** workflow from the left sidebar.
3. Click **Run workflow** on the right side.
4. Customize your build parameters (choose your source, enable KernelSU if desired, pick a performance profile, etc.).
5. Click **Run workflow** and track the progress in real time.
6. Download your custom flashable zip from the repository's **Releases** page once finished.

---

> [!NOTE]
> Ensure your repository has **Read and write permissions** enabled under *Settings > Actions > General > Workflow permissions* so the action can successfully publish releases and upload files.
