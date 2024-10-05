# Embedded MicroPython from Ground Up™

## Description

- Course Material = https://study.embeddedexpert.io/courses/enrolled/1872792

## Course Material

### Python Essential Training

### Setting Up MicroPython

#### Getting the Required Tools

- Download the DFU, search for `micropython nucleo-f411 dfu`, you will find on top of the search [https://micropython.org/download/NUCLEO_F411RE/](https://micropython.org/download/NUCLEO_F411RE/), or if you want to see the list board that available using MicroPython visit this link [https://micropython.org/download/](https://micropython.org/download/)
  - Currently the course use `v1.19.1 (2022-06-18) .dfu` so choose this `dfu` version and download from this link [v1.19.1 (2022-06-18) .dfu](https://micropython.org/resources/firmware/NUCLEO_F411RE-20220618-v1.19.1.dfu)
  - Store the downloaded `NUCLEO_F411RE-20220618-v1.19.1.dfu` in the course folder. We cannot flash directly to the device therefore we need a **STM32 DFUSE**, search for `stsw-stm32080 dfuse` and [download from this link](https://www.st.com/en/development-tools/stsw-stm32080.html). Another way is to use `stm32cubeprogrammer` which can be [downloaded from this link](https://www.st.com/en/development-tools/stm32cubeprog.html)

#### Installing the Required Tools
