<div align="center">

# Sunone Aimbot C++
[![C++](https://img.shields.io/badge/C%2B%2B-17-blue)](https://github.com/SunOner/sunone_aimbot_cpp)
[![License MIT](https://badgen.net/github/license/SunOner/sunone_aimbot_cpp)](https://github.com/SunOner/sunone_aimbot_cpp/blob/main/LICENSE)
[![Github stars](https://img.shields.io/github/stars/SunOner/sunone_aimbot_cpp?color=ffb500)](https://github.com/SunOner/sunone_aimbot_cpp)
[![Discord server](https://badgen.net/discord/online-members/sunone)](https://discord.gg/sunone)
  <p>
    <a href="https://github.com/SunOner/sunone_aimbot_cpp/releases" target="_blank">
      <img width="75%" src="https://github.com/SunOner/sunone_aimbot/blob/main/media/one.gif"></a>
  </p>
</div>

- **This project is actively being developed thanks to the people who support on [Boosty](https://boosty.to/sunone) and [Patreon](https://www.patreon.com/sunone). By providing active support, you receive enhanced AI models.**

## How to Use

1. **Download the Latest Release**  
   Download the latest release from [here](https://github.com/SunOner/sunone_aimbot_cpp/releases).

2. **Download TensorRT**  
   Get TensorRT from [Yandex](https://disk.yandex.ru/d/S16C9oDSuF1_EQ) or [Developer Nvidia](https://developer.nvidia.com/tensorrt/download/10x).

3. **Unpack TensorRT and Aimbot**  
   Extract the contents of both TensorRT and the Aimbot.

4. **Copy DLL Files**  
   - Copy `TensorRT-10.6.0.26/lib/nvinfer_10.dll` to `sunone_aimbot_cpp/`.
   - Copy all files from `TensorRT-10.6.0.26/lib/` to `TensorRT-10.6.0.26/bin/`.

5. **Transfer the ONNX Model**  
   Copy `sunone_aimbot_cpp/models/sunxds_0_5_6.onnx` to `TensorRT-10.6.0.26/bin/`.

6. **Generate Engine File**  
   Open Command Prompt in `TensorRT-10.6.0.26/bin/` and execute:
   ```bash
   trtexec.exe --onnx=sunxds_0.5.6.onnx --saveEngine=sunxds_0.5.6.engine --fp16
   ```

7. **Finalize Setup**  
   After the export (~1-5 minutes), copy `TensorRT-10.6.0.26/bin/sunxds_0.5.6.engine` to `sunone_aimbot_cpp/models/`.

8. **Run the Application**  
   Execute `ai.exe`.

> **⚠️ WARNING:** TensorRT version 10 does not support the Pascal architecture (10 series graphics cards). Use only with GPUs of at least the 20 series.

> **ℹ️ NOTE:** This guide is intended for advanced users. If you encounter errors while building the modules, please report them on the [Discord server](https://discord.gg/sunone).

## 📺 Installation Video

[![Watch the Installation Tutorial](https://img.youtube.com/vi/EyPtfXLhiuo/0.jpg)](https://www.youtube.com/watch?v=EyPtfXLhiuo)

Click the image above to watch the installation tutorial video.

## 🛠 Build the Project from Source

1. **Install Visual Studio 2019 Community**  
   Download and install from the [official website](https://visualstudio.microsoft.com/vs/community/).

2. **Install Windows SDK**  
   Ensure you have Windows SDK version **10.0.26100.0** installed.

3. **Install CUDA and cuDNN**  
	- **CUDA 12.4**  
		Download from [NVIDIA CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit).
	- **cuDNN 9.1**  
		Available on the [NVIDIA cuDNN](https://developer.nvidia.com/cudnn) website.

4. **Set Up Project Structure**  
	Create a folder named `modules` in the directory `sunone_aimbot_cpp\sunone_aimbot_cpp\modules`.

5. **Download Required Libraries**  
   - [Boost](https://disk.yandex.ru/d/O8XkcKeQ3vNDFg)
   - [OpenCV](https://github.com/opencv/opencv/releases/tag/4.10.0) (Windows)
   - TensorRT from [Yandex](https://disk.yandex.ru/d/S16C9oDSuF1_EQ) or [Developer Nvidia](https://developer.nvidia.com/tensorrt/download/10x)

6. **Extract Libraries**  
	Extract the downloaded libraries into the respective directories:
		- `sunone_aimbot_cpp\sunone_aimbot_cpp\modules\boost_1_82_0`
		- `sunone_aimbot_cpp\sunone_aimbot_cpp\modules\opencv` *(Rename `opencv-4.10.0` to `opencv`)*
		- `sunone_aimbot_cpp\sunone_aimbot_cpp\modules\TensorRT-10.6.0.26`

7. **Compile Boost Libraries**  
	- Navigate to the Boost directory:
	```bash
	cd sunone_aimbot_cpp/sunone_aimbot_cpp/modules/boost_1_82_0
	```
	- Run the bootstrap script:
	```bash
	bootstrap.bat vc142
	```
	- After successful bootstrapping, build Boost:
	```bash
	b2.exe --build-type=complete link=static runtime-link=static threading=multi variant=release
	```
	
8. **Configure Project Settings**  
	- Open the project in Visual Studio.
	- Ensure all library paths are correctly set in **Project Properties** under **Library Directories**.
	- Go to Nuget packages and install `Microsoft.Windows.CppWinRT`.
	
9. **Verify CUDA Integration**  
	- Right-click on the project in Visual Studio.
	- Navigate to **Build Dependencies** > **Build Customizations**.
	- Ensure that **CUDA 12.4** (.targets, .props) is included.
	
10. **Build the Project**  
	- Switch the build configuration to **Release**.
	- Build the project by selecting **Build** > **Build Solution**.

## 📋 Config docs
- The config documentation is available in a separate [repository](https://github.com/SunOner/sunone_aimbot_docs/blob/main/config/config_cpp.md).

## 📚 References

- [TensorRT Documentation](https://docs.nvidia.com/deeplearning/tensorrt/)
- [OpenCV Documentation](https://docs.opencv.org/4.x/d1/dfb/intro.html)
- [Windows SDK](https://developer.microsoft.com/en-us/windows/downloads/windows-sdk/)
- [Boost](https://www.boost.org/)
- [ImGui](https://github.com/ocornut/imgui)
- [CppWinRT](https://github.com/microsoft/cppwinrt)
- [Python AI AIMBOT](https://github.com/SunOner/sunone_aimbot)

## 📄 Licenses

### Boost
- **License:** [Boost Software License 1.0](https://www.boost.org/LICENSE_1_0.txt)

### OpenCV
- **License:** [Apache License 2.0](https://opencv.org/license.html)

### ImGui
- **License:** [MIT License](https://github.com/ocornut/imgui/blob/master/LICENSE)