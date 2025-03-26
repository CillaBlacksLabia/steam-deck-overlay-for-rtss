# Steam Deck Performance Overlay for RivaTuner Statistics Server (RTSS)

For those that love the MangoHud overlay used on the Steam Deck, heres my interpretation of it using RTSS for Windows

![SteamDeckPreset_4](https://github.com/user-attachments/assets/717c5f1e-5974-4a2f-88b5-9731803559d0)
&nbsp;

&nbsp;





## Performance Overlay
Preset 1  
![Preset_1](https://github.com/user-attachments/assets/fda8ee5b-d30c-42b1-91e8-8e2ef5343315)

Preset 2  
![Preset_2](https://github.com/user-attachments/assets/1793e00a-039c-4346-b119-db7cf9ac0490)

Preset 3  
![Preset_3](https://github.com/user-attachments/assets/030c7ea0-5627-4bdb-8c3c-aa58f4cd8f49)

Preset 4  
![Preset_4](https://github.com/user-attachments/assets/8b78f2d3-106e-4056-8151-4671ec0b8352)
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

#### SteamDeckPreset_1
> Nothing here
&nbsp;

&nbsp;
#### SteamDeckPreset_2
> Nothing here
&nbsp;

&nbsp;
#### SteamDeckPreset_3

Data provider, select **HWiNFO64**  
Under the following sections, tick:

CPU [#0]: YOUR_CPU_NAME
>Average Effective Clock  

![preset3-overlay-data-sources](https://github.com/user-attachments/assets/88b0a37c-5ae4-444b-a5ad-d5071f040015)
&nbsp;

&nbsp;
#### SteamDeckPreset_4

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
> 
![preset4-overlay-data-sources](https://github.com/user-attachments/assets/e5534f11-2791-499f-8f56-dae92ad6f048)
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

![data-source-settings](https://github.com/user-attachments/assets/cdf3a135-80c9-461b-9cb7-283eec109ce4)
