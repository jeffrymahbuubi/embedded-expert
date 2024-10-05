# Embedded MicroPython from Ground Up™

## Description

- Course Material = https://study.embeddedexpert.io/courses/enrolled/1872792

## Course Material

### Python Essential Training

### Setting Up MicroPython

#### Getting the Required Tools

- Step 1: Download the DFU file by searching for `micropython nucleo-f411 dfu`. The top search result should be [this link](https://micropython.org/download/NUCLEO_F411RE/). For a list of boards compatible with MicroPython, visit [this link](https://micropython.org/download/).
  - The course currently uses `v1.19.1 (2022-06-18) .dfu`. Download this version from [here](https://micropython.org/resources/firmware/NUCLEO_F411RE-20220618-v1.19.1.dfu).
- Step 2: Store the downloaded `NUCLEO_F411RE-20220618-v1.19.1.dfu` file in the course folder. Direct flashing to the device is not possible, so we need **STM32 DFUSE**. Search for `stsw-stm32080 dfuse` and [download it from this link](https://www.st.com/en/development-tools/stsw-stm32080.html). Alternatively, you can use `stm32cubeprogrammer`, which can be [downloaded from this link](https://www.st.com/en/development-tools/stm32cubeprog.html).
- Step 3: Install the `stm32cubeprogrammer` and uncheck the `SM32TrustedPackageCreator` option, keeping the rest of the settings the same.
- Step 4: Install the `stsw-stm32080 dfuse`. After installation, search for `Dfu file manager` and select `I want to extract S19, HEX or BIN files from a DFU one`. Upload the `.dfu` file and choose `Hex` in the extraction options.
- Step 5: Open the `STM32CubeProgrammer`, connect your board, and click `Connect`. Upload the `.hex` file generated from the `Dfu file manager` by selecting `Open file` and then clicking `Download`. A message saying `File download complete` will appear. Finally, disconnect the board by clicking `Disconnect`.
  - Ensure the device is disconnected when installing `Cube Programmer`.
  - To revert the board to a C environment, you can flash it using any Cube IDE or Cube MX.

#### Accessing the Microcontroller using a Terminal

- There are several options to access the board. One option is:

  - [Tera Term](https://github.com/TeraTermProject/teraterm/releases)
    - After installation, change the font size by selecting `Setup` ➡️ `Font` and setting it to `12`.
    - Change the baud rate to `115200` by selecting `Setup` ➡️ `Serial port` ➡️ `Baud Rate` and setting it to `115200`. Check the `COM Port` your device is connected to in `Device Manager`, then select the appropriate `COM Port` in Tera Term. Finally, choose `New Setting` and press `Reset` on your board.
  - Using `rshell`:
    - Open your terminal (PowerShell or CMD), create a virtual environment, and run `pip install rshell`.
    - Activate `rshell` by typing `rshell`, then connect to the board by running `connect serial COM4`. Copy the file by typing `cp Source/flash/main.py`.
    - Type `repl` to enter the Python environment. You can use `help()`, similar to the options available in `Tera Term`.
  - [Thonny](https://thonny.org/)

    - I chose to download the `Portable Version` to avoid installing it on my PC.
    - Create a file named `0_test.py` and populate it with the provided code to test the connection:

      ```python
      import pyb

      def main():
        print("Hello from STM32")

      main()
      ```

    - Choose `Run`, then select `Configure interpreter`. Choose `MicroPython (generic)` and select your device's `Port`. Finally, click `Configure` ➡️ `Run interpreter`.

#### Installing the Required Tools
