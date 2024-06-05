# Server System Setup

Scout can be configured a number of ways, some of which require additional system setup.

## Ubuntu

$$INFO
title: Info
The following Ubuntu installation tutorial is provided to assist users unfamiliar with Linux installation, but is not covered under our support services. Should you encounter problems, seek resources in the Linux community online.
$$

Make sure that the laptop is connected to a fast and stable internet connection. Software download is required during this process, and some of the downloaded components may be > 2 GB.
Obtain a thumb drive (8GB minimum) to store downloaded files for the Ubuntu operating system.

### Download Ubuntu OS Image

$$WARNING
title: WARNING
This process wipes the server of all existing content to install the Ubuntu Linux operating system. Ensure all existing content is backed up before proceeding.
$$

Install Ubuntu as the only OS on the laptop; dual boot configurations are not supported. The following instructions are for version 20.04.

1. On a separate computer, open a web browser and navigate to the [Ubuntu 20.04 release page](https://releases.ubuntu.com/20.04.5/).
2. Download the [ISO Desktop image](https://releases.ubuntu.com/20.04.5/ubuntu-20.04.5-desktop-amd64.iso).
3. Use the [thumb drive to create a Ubuntu installation tool](https://ubuntu.com/tutorials/create-a-usb-stick-on-ubuntu#1-overview).

### Install Ubuntu OS Image from USB

$$WARNING
title: WARNING
This step deletes all data, including the original OS, from the laptop.
$$

To install Ubuntu Linux as the operating system on the Scout Server laptop:

1. Plug the thumb drive with the downloaded Ubuntu image into the Scout Server laptop.
2. Restart the laptop.
3. On restart, press the **F12** key for the boot menu.
4. Select the USB drive and boot to the USB.
5. On a separate computer, open the [Install support guide](https://ubuntu.com/tutorials/install-ubuntu-desktop#4-boot-from-usb-flash-drive). Start with Step 4.
6. Select **Normal Installation** and check both of the following:
    * Download updates while installing Ubuntu
    * Install third-party software for graphics and Wi-Fi hardware and additional media formats
7. Select **Erase disk and install Ubuntu**
8. Once installation is complete, restart the computer and remove the thumb drive.

### First-time Ubuntu configuration

After the Ubuntu Linux boots for the first time, select the following options during its initial configuration questions:

1. Click **Next** on Livepatch to skip setup.
2. When prompted with Help improve Ubuntu, select **No** before clicking **Next**.
3. **Allow** Location Services, then click **Next**.
4. Click **Next** on Privacy.

***

## Storage

Scout is designed to process large volumes of aerial survey imagery, which may come in terabytes. Ensure you have adequate image storage available.

1. Create a directory for image storage, such as `/data/scout`
	- Subsequent instructions in this documentation refers to the path as `/data/scout` for all file creation. 
1. Create a subfolder in the directory such as `/data/scout/images` which will store images that will be added to Scout.
	- As soon as this subfolder is created, you can begin copying your images into it.
1. The first should be for data storage. We recommend `/data/scout/db`
1. The second is for temporary use during processing. We recommend `/data/scout/tmp`

***

### CUDA toolkit

To update your system’s CUDA Toolkit:

1. Visit [CUDA Toolkit resources](https://developer.nvidia.com/cuda-downloads?target_os=Linux&amp;amp;target_arch=x86_64&amp;amp;Distribution=Ubuntu)
1. Select the version of Ubuntu you are using.
1. Select **deb(local)** for your installer type.
1. Follow the download instructions for the toolkit installation.
1. Follow the download instructions for the driver installation.
1. Once installed, you will need to reboot the server to ensure the toolkit is available.

### NVIDIA Docker

Ensure Docker is installed and the daemon is running.
To install NVIDIA Docker:
1. Visit [NVIDIA Docker resources](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker).
1. Follow the Installation instructions.
1. Follow the Configuring Docker instructions.

### Verify GPU compute with ScoutBot demo

From the Terminal window, you can test GPU execution on the laptop by executing some of Scout’s GPU-enabled ML capabilities.

1. Run the following command: `docker run -it --rm --gpus all -p 5000:7860 wildme/scoutbot:main python3 app2.py`
2. Open a separate Terminal window to watch GPU performance.
3. Press CTRL-C to end the test.