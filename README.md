
# WiZ Light Frequency Audio Visualizer Installer

This repository contains a program that provides dynamic control and visualization of WiZ lights using audio frequencies. It combines a graphical user interface (GUI) for configuration with a powerful C++ backend for real-time audio processing and light control.

## Features

### **Graphical User Interface**
- **Easy Configuration:** Use the GUI to configure light settings, including IP addresses, effects, and colors.
- **Device Selection:** Allows manual or dropdown selection of audio input devices.
- **Advanced Settings:** Fine-tune advanced options like sample rates, frame sizes, brightness thresholds, and more.
- **Reset to Defaults:** Restore default settings with a single click.

### **Audio Visualizer**
- **Real-Time Frequency Mapping:** Maps audio frequencies to light colors in real-time.
- **Dynamic Brightness Control:** Adjusts brightness based on audio energy levels.
- **Customizable Colors:** Supports user-defined color palettes for frequency changes.
- **Smooth Transitions:** Enables or disables smooth color transitions for effects.
- **Beat Detection:** Triggers light changes based on dynamic thresholds.

### **Installation**
- **Installer Included:** A single installer sets up the GUI and the backend C++ program, ready to run.
- **Configurable Paths:** Simplifies deployment with easy-to-edit configuration files.

### **Light Effects**
- **Color Changes:** Dynamically change light colors based on audio frequency.
- **Brightness Adjustment:** Automatically adjust light brightness according to energy levels.
- **On/Off Switching:** Trigger lights to turn on or off in response to beats or silence.

### **Calibration**
- **Silence Threshold Calibration:** Automatically adjusts the silence threshold to account for varying noise levels.
- **Dynamic Gain Control:** Ensures consistent light response across different audio volumes.

### **Customization**
- **Configurable JSON Files:** Allows advanced users to directly modify `config.json` for granular control.
- **Flexible Effects:** Choose between color changes, brightness adjustments, or turning lights on/off.

## How to Use

1. **Install the Program**: Run the installer and follow the prompts to set up the program.
2. **Launch the GUI**: Use the provided GUI executable to configure your settings.
3. **Connect Your Lights**: Ensure your WiZ lights are on the same network as your PC.
4. **Set Up Your Audio Device**: Follow the guide below to configure your audio device.
5. **Run the Visualizer**: Start the visualizer from the GUI or by running the backend C++ program.

---

## Configuring Your Audio Device

### **Option 1: Using Stereo Mix (if available)**
1. **Enable Stereo Mix**:
   - Right-click on the speaker icon in the taskbar and select **Sounds**.
   - Go to the **Recording** tab.
   - If you see "Stereo Mix," right-click and select **Enable**.
2. **Set as Default Device**:
   - Right-click "Stereo Mix" and choose **Set as Default Device**.
3. **Select Stereo Mix in the Program**:
   - Open the GUI and select "Stereo Mix" as the audio input device.

---

### **Option 2: Installing VB Audio Cable and Voicemeeter**

#### **Step 1: Download and Install VB Audio Cable**
1. **Download VB Audio Cable**:
   - Visit the [VB Audio Cable website](https://vb-audio.com/Cable/) and download the free VB-CABLE package.
2. **Install VB Cable**:
   - Run the installer as an administrator and follow the on-screen instructions.
   - Restart your computer after installation.

#### **Step 2: Download and Install Voicemeeter**
1. **Download Voicemeeter**:
   - Go to the [Voicemeeter website](https://vb-audio.com/Voicemeeter/) and download the "Voicemeeter Banana" or "Voicemeeter" application.
2. **Install Voicemeeter**:
   - Run the installer as an administrator and follow the on-screen instructions.
   - Restart your computer after installation.

#### **Step 3: Configure VB Audio Cable and Voicemeeter**
1. **Set Up VB Audio Cable**:
   - Open the Windows **Sound Settings** (right-click the speaker icon > Sounds > Recording tab).
   - Set "VB-Audio Cable Output" as the default recording device.
2. **Open Voicemeeter**:
   - Launch the Voicemeeter application.
3. **Configure Hardware Input**:
   - In Voicemeeter, under **Hardware Input 1**, select your physical microphone or audio source.
4. **Configure Hardware Output**:
   - Under **Hardware Out**, select your default audio playback device (e.g., your headphones or speakers).
5. **Route Audio Through VB Cable**:
   - Set **Hardware Input 2** to "CABLE Output (VB-Audio Cable)."
   - Enable the "B1" button for Hardware Input 2 to route the audio to the VB Audio Cable.
6. **Set Up in the Program**:
   - In the GUI, select "VB-Audio Cable Output" as the audio input device.

#### **Step 4: Save Your Settings**
- Save your Voicemeeter configuration to ensure it loads automatically with your preferred routing.

---

### Command-Line Options
- `--calibrate`: Calibrate the silence threshold for improved accuracy.
  - Example: `visualizer.exe --calibrate --duration=10`
- `--duration`: (Optional) Specify the duration for calibration in seconds.

---

## System Requirements
- **Operating System**: Windows 10 or later.
- **Dependencies**: Installed with the program:
  - PortAudio
  - FFTW3
  - Boost Asio
- **WiZ Lights**: Requires WiZ smart lights connected to the same network.

## Configuration File
The program uses `config.json` for storing settings. Key options include:
- `audio_device`: Name of the audio input device.
- `advanced_settings`: Contains options like `SAMPLE_RATE`, `FRAMES_PER_BUFFER`, and more.
- `lights`: Define each light’s IP, effect, and color settings.

## Known Issues
- Duplicate entries may appear in the light list if names are renamed and refreshed.
- White color display inconsistencies in some scenarios.
- Lights not on the network will not respond but are displayed in the preview.

## Contributions
Contributions to improve functionality or address issues are welcome. Please submit pull requests or open issues for discussion.
