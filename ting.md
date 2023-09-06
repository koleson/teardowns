# Ting Fire WL-T-3000-R07

**CPU:**  [NXP LPC4370FET100](https://www.nxp.com/part/LPC4370FET100#/)
 - 32-bit ARM Cortex-M4 + 2 M0 MCUs
 - 80 Msps 12-bit ADC
 - A lot of peripherals!
 - $5.36 each in qty 10k as of September 2023
**Connectivity:**  Laird Sterling SQG-EWB1 802.11b/g/n + Bluetooth + BLE module with integrated MCU
 - IPEX to PCB antenna
 - Alternate part listed on label:  Inventek FCC ID O7P-4343
**Other ICs:**
 - [Texas Instruments SN74LVC126A Quadruple Bus Buffer Gate](https://www.ti.com/lit/ds/symlink/sn74lvc126a.pdf?ts=1693883286240)
 - [NXP PCT2075 digital temperature sensor and thermal watchdog, I2C](https://www.nxp.com/docs/en/data-sheet/PCT2075.pdf)
 - [Power Integrations LNK623 AC/DC switching power supply controller](https://www.mouser.com/datasheet/2/328/linkcv_family_datasheet-1083.pdf)


## Other Notes

It seems like almost all of the interesting work done here happens on the NXP CPU - the high-sample-rate ADC built into it doesn't seem like a coincidence.

I haven't proxied this device comprehensively yet, so it's not clear how much processing is done locally versus in the cloud.  Streaming the data as-captured or even downsampled would be great for backtesting algorithm changes and so on, but would also render the device pretty useless during a service outage.

It seems likely that nearly all data is captured and processed locally, then nearly all of it is discarded, with only anomalous waveform captures being sent to the cloud.

The live voltage meter updates about once per second, but that's probably sent as a snapshot rather than being derived from the waveform capture.
