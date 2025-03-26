# Steam Deck Performance Overlay for RivaTuner Statistics Server (RTSS)

For those that love the MangoHud overlay used on the Steam Deck, heres my interpretation of it using RTSS for Windows

![SteamDeckPreset_4](https://github.com/user-attachments/assets/c298d187-66cd-432a-8d2e-bcec748d5e0c)

Download [all presets in 1 zip](https://github.com/CillaBlacksLabia/steam-deck-overlay-for-rtss/releases/tag/v0.1.0) or download individually below

## Contents  
* [Performance Overlay examples](#performance-overlay-examples)  
* [Programs needed](#programs-needed)  
* [HWiNFO](#hwinfo)  
  - [HWiNFO setup](#hwinfo-setup)  
* [RTSS](#rtss)  
  - [RTSS layouts](#rtss-layouts)  
  - [RTSS adding Data Sources](#rtss-adding-data-sources)  
* [Hotkeys](#hotkeys)  
* [Benchmarking](#benchmarking)
&nbsp;

&nbsp;





## Performance Overlay examples
### Preset1  
![Preset_1](https://github.com/user-attachments/assets/5a28530e-d797-45dd-b4dc-e94c14424bb7)  
[Download preset 1](https://github.com/CillaBlacksLabia/steam-deck-overlay-for-rtss/releases/tag/preset1-v0.1.0)

### Preset2  
![Preset_2](https://github.com/user-attachments/assets/22e13b4d-d001-4985-909f-57e5ad561145)  
[Download preset 2](https://github.com/CillaBlacksLabia/steam-deck-overlay-for-rtss/releases/tag/preset2-v0.1.0)

### Preset 3  
![Preset_3](https://github.com/user-attachments/assets/e31b5996-dbb3-4402-90fe-c26c9385b1a1)  
[Download preset 3](https://github.com/CillaBlacksLabia/steam-deck-overlay-for-rtss/releases/tag/preset3-v0.1.0)

### Preset 4  
![Preset_4](https://github.com/user-attachments/assets/08f9e795-5eac-4a85-a4ee-9561a65004f9)  
[Download preset 4](https://github.com/CillaBlacksLabia/steam-deck-overlay-for-rtss/releases/tag/preset4-v0.1.0)
&nbsp;

&nbsp;





## Programs needed

Guru3D RTSS Rivatuner Statistics Server
[www.guru3d.com](https://www.guru3d.com/download/rtss-rivatuner-statistics-server-download/)

HWiNFO
[www.hwinfo.com](https://www.hwinfo.com/download/)
&nbsp;

&nbsp;





## HWiNFO

### HWiNFO setup
>1. Right click icon in system tray, select **Settings**
>2. Check box for **Shared Memory Support**
&nbsp;

&nbsp;





## RTSS

### RTSS layouts
.ovl files go in **Overlays** folder
> Default location - C:\Program Files (x86)\RivaTuner Statistics Server\Plugins\Client\Overlays

Open RTSS
> Setup > Plugins (tab) > OverlayEditor.dll > Layouts > Load
&nbsp;

&nbsp;





### RTSS adding Data Sources

In **Overlay editor**
> DataSources > Add *button*
&nbsp;

&nbsp;


**SteamDeckPreset_1**

> Nothing here
&nbsp;

&nbsp;


**SteamDeckPreset_2**

> Nothing here
&nbsp;

&nbsp;


**SteamDeckPreset_3**

Data provider, select **HWiNFO64**  
Under the following sections, tick:

CPU [#0]: YOUR_CPU_NAME
>Average Effective Clock

![preset3-overlay-data-sources](https://github.com/user-attachments/assets/8f6b3d58-0793-4329-a9a4-5ff215f9e770)
&nbsp;

&nbsp;


**SteamDeckPreset_4**

Data provider, select **HWiNFO64**  
Under the following sections, tick:


**CPU [#0]: YOUR_CPU_NAME**
> Average Effective Clock

Network: YOUR_NETWORK_CARD_NAME
> Current UP rate  
> Current DL rate

YOUR_MOTHERBOARD_NAME (There may be multiple entries, select the first instance the values are the same)
> Current (IIN)  
> Current (IOUT)  
> Power (Input)  
> Power (POUT)  
> PUMPFAN              <-- Might be named differently  
> System 1,2,3 etc...  <-- Might be named differently

![preset4-overlay-data-sources](https://github.com/user-attachments/assets/73384f2f-e1f9-4677-9492-2dbb310a0db9)
&nbsp;

&nbsp;





## Hotkeys

In RTSS go to:
> 1. Setup > Plugins (tab) > HotkeyHandler.dll
> 2. Under 'On-Screen Display', click **Configure** *button*

I use F9-F11 but you can use whatever keys you like  
![overlay-editor-plugin-properties](https://github.com/user-attachments/assets/a04aa6ac-4cca-482f-960e-f29620a1fbb3)

Click each **...** *button* and enter each .ovl filename in Parameters. You can change the description too  
![programmable-overlay-modifier-properties](https://github.com/user-attachments/assets/93f13f55-0f13-462e-8193-6230ca43496e)
&nbsp;

&nbsp;





## Benchmarking

In RTSS go to:
> 1. Setup > Plugins (tab) > HotkeyHandler.dll
> 2. Under 'Benchmark', set hotkeys for **begin recording** and **end recording**
> 3. Okay (button)

In Plugins *tab*
> OverlayEditor.dll

In **Overlay editor**:
> DataSources > Add *button*  
> Data provider, select **Internal HAL**


Under SYS section:
> 1. Select **Stub**
> 2. Okay *button*
> 3. Double-click **Stub**
> 4. Enter the following:  
     * ID                 > IsBenchmarkActive  
     * Name               > IsBenchmarkActive  
     * Correction formula > (rtssflags & 0x100) != 0
> 5. Okay *button*

![data-source-settings](https://github.com/user-attachments/assets/e763f429-402a-4e06-83d8-fe6a4df01580)
