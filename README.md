Davinci Jr 1.0w reverse engineering:

# Forum:
http://www.soliforum.com/topic/13769/davinci-jr-repetier-port/

# Main Components:
1. AT SAM4E8E: supported by klipper
2. lpc1115: not supported by klipper
 * REPORTED: Be careful if power on after wipe the FW, the extruder is on and heating without any control, you better disconnect it

# Factory Reset:
There are three pads for erase and reset switches on the motherboard.

they can be populated with:
http://allegro.pl/tact-switch-3x6x4-3mm-smd-10szt-i6433890340.html

short between TP89 and TP88 and power on for a few seconds to clear flash.

# Flashing:
'bain' is the tool for flashing the SAM4E8E

# BootLoaders:
1.
2. the LPC111x series has a built in bootloader:
 * https://www.reprap-diy.com/lpc1114_bootloader
 * https://community.nxp.com/t5/LPCXpresso-IDE/LPC1115-UART-ISP-connection/m-p/593238
 
# Supplied pinout:

|Pin|Type|MCU|Pin Descriptor|PIO type|Function|MCU|Descriptor|
|---|---|---|---|---|---|---|---|
|106|MASK||PIO_PA5C_URXD1/PIO_PA6C_UTXD1|N/A|||
|105|MASK||PIO_PA9A_URXD0/PIO_PA10A_UTXD0|N/A|||
|104|MASK||PIO_PA3A_TWD0/PIO_PA4A_TWCK0|N/A|||
|103|MASK||PIO_PA28C_MCCDA/PIO_PA30C_MCDA0/PIO_PA31C_MCDA1/PIO_PA26C_MCDA2/PIO_PA27C_MCDA3|N/A|||
|102|Pin|129|PIO_PA29C_MCCK|PIO_PERIPH_C||||
|101|Pin|28|PIO_PE5|PIO_OUTPUT_0|Up Key|||
|100|Pin|27|PIO_PE4|PIO_OUTPUT_0|Right Key|||
|99|Pin|10|PIO_PE3|PIO_INPUT||62|PA26|
|98|Pin|7|PIO_PE2|PIO_INPUT||70|PA27|
|97|Pin|6|PIO_PE1|PIO_INPUT||79|PB6|
|96|Pin|4|PIO_PE0|PIO_INPUT||89|PB7
|95|Pin|2|PIO_PD31|PIO_INPUT||87|PB12|Erase
|94|Pin|34|PIO_PD30|PIO_OUTPUT_0|Home Key|105|PB4
|93|Pin|108|PIO_PD29|PIO_INPUT||109|PB5
|92|Pin|71|PIO_PD28|PIO_OUTPUT_0||112|PA28
|91|Pin|47|PIO_PD27|PIO_OUTPUT_0||116|PA30
|90|Pin|53|PIO_PD26|PIO_OUTPUT_0||118|PA31
|89|Pin|52|PIO_PD25|PIO_OUTPUT_0||136|PB10
|88|Pin|54|PIO_PD24|PIO_OUTPUT_0||137|PB11
|87|Pin|57|PIO_PD23|PIO_OUTPUT_0|Inside LED on/Off|141|PB8
|86|Pin|60|PIO_PD22|PIO_OUTPUT_0||142|PB9
|85|Pin|63|PIO_PD21|PIO_OUTPUT_0|||
|84|Pin|65|PIO_PD20|PIO_OUTPUT_0|||
|83|Pin|67|PIO_PD19|PIO_OUTPUT_0|||
|82|Pin|69|PIO_PD18|PIO_OUTPUT_0|||
|81|Pin|74|PIO_PD17|PIO_OUTPUT_0|||
|80|Pin|78|PIO_PD16|PIO_OUTPUT_0|Extruder Enable||
|79|Pin|106|PIO_PD15|PIO_OUTPUT_0|||
|78|Pin|84|PIO_PD14|PIO_OUTPUT_0|||
|77|Pin|88|PIO_PD13|PIO_OUTPUT_0|||
|76|Pin|92|PIO_PD12|PIO_OUTPUT_0|||
|75|Pin|98|PIO_PD11|PIO_OUTPUT_0|||
|74|Pin|101|PIO_PD10|PIO_INPUT|||
|73|Pin|110|PIO_PD9|PIO_OUTPUT_0|Y end stop||
|72|Pin|113|PIO_PD8|PIO_OUTPUT_0|X end stop||
|71|Pin|119|PIO_PD7|PIO_OUTPUT_0|||
|70|Pin|121|PIO_PD6|PIO_OUTPUT_0|Enable Z||
|69|Pin|125|PIO_PD5|PIO_OUTPUT_0|Enable Y||
|68|Pin|126|PIO_PD4|PIO_OUTPUT_0|||
|67|Pin|128|PIO_PD3|PIO_OUTPUT_0|Enable X||
|66|Pin|131|PIO_PD2|PIO_OUTPUT_0|||
|65|Pin|132|PIO_PD1|PIO_OUTPUT_0|||
|64|Pin|1|PIO_PD0|PIO_OUTPUT_0|||
|63|Pin|14|PIO_PC31X1_AFE0_AD11|PIO_INPUT|ADC11||
|62|Pin|15|PIO_PC30X1_AFE0_AD10|PIO_INPUT|ADC10||
|61|Pin|16|PIO_PC29X1_AFE0_AD9|PIO_INPUT|ADC9||
|60|Pin|76|PIO_PC28|PIO_OUTPUT_0|||
|59|Pin|12|PIO_PC27X1_AFE0_AD13|PIO_INPUT|ADC13||
|58|Pin|13|PIO_PC26B_TIOA4|PIO_PERIPH_B|||
|57|Pin|133|PIO_PC25|PIO_OUTPUT_0|||
|56|Pin|130|PIO_PC24|PIO_INPUT|||
|55|Pin|127|PIO_PC23B_TIOA3|PIO_PERIPH_B|||
|54|Pin|124|PIO_PC22|PIO_OUTPUT_0|||
|53|Pin|122|PIO_PC21|PIO_INPUT|||
|52|Pin|120|PIO_PC20|PIO_OUTPUT_0|||
|51|Pin|117|PIO_PC19|PIO_OUTPUT_0|Z end stop||
|50|Pin|111|PIO_PC18|PIO_OUTPUT_0|LCD ???||
|49|Pin|103|PIO_PC17|PIO_OUTPUT_0|||
|48|Pin|100|PIO_PC16|PIO_INPUT|||
|47|Pin|18|PIO_PC15X1_AFE0_AD7|PIO_INPUT|ADC7||
|46|Pin|97|PIO_PC14|PIO_OUTPUT_0|||
|45|Pin|19|PIO_PC13X1_AFE0_AD6|PIO_INPUT|ADC6||
|44|Pin|17|PIO_PC12X1_AFE0_AD8|PIO_INPUT|ADC8||
|43|Pin|94|PIO_PC11B_TIOA8|PIO_PERIPH_B|||
|42|Pin|90|PIO_PC10|PIO_OUTPUT_0|LCD light On/Off||
|41|Pin|86|PIO_PC9|PIO_OUTPUT_0|||
|40|Pin|82|PIO_PC8B_TIOA7|PIO_PERIPH_B|||
|39|Pin|48|PIO_PC7|PIO_OUTPUT_0|||
|38|Pin|54|PIO_PC6|PIO_OUTPUT_0|||
|37|Pin|58|PIO_PC5B_TIOA6|PIO_PERIPH_B|LCD???||
|36|Pin|41|PIO_PC4X1_AFE1_AD7|PIO_INPUT|ADC23||
|35|Pin|40|PIO_PC3B_PWML3|PIO_PERIPH_B|PWM_CH3||
|34|Pin|39|PIO_PC2|PIO_OUTPUT_0|||
|33|Pin|38|PIO_PC1X1_AFE1_AD4|PIO_INPUT|ADC20/LCD ???||
|32|Pin|11|PIO_PC0|PIO_INPUT|ADC14||
|31|Pin|140|PIO_PB14X1_DAC1|PIO_OUTPUT_0|DA1||
|30|Pin|144|PIO_PB13C_SCK0|PIO_PERIPH_C|||
|29|Pin|31|PIO_PB3X1_AFE1_AD1|PIO_INPUT|Left Key||
|28|Pin|26|PIO_PB2|PIO_OUTPUT_0|||
|27|Pin|20|PIO_PB1C_TXD0|PIO_PERIPH_C|||
|26|Pin|21|PIO_PB0C_RXD0|PIO_PERIPH_C|||
|25|Pin|59|PIO_PA25|PIO_OUTPUT_0|||
|24|Pin|56|PIO_PA24|PIO_OUTPUT_0|||
|23|Pin|46|PIO_PA23A_SCK1|PIO_PERIPH_A|||
|22|Pin|37|PIO_PA22A_TXD1|PIO_PERIPH_A|||lvds
|21|Pin|32|PIO_PA21A_RXD1|PIO_PERIPH_A|Down Key||
|20|Pin|22|PIO_PA20B_PWML1|PIO_PERIPH_B|PWM_CH1||
|19|Pin|23|PIO_PA19B_PWML0|PIO_PERIPH_B|PWM_CH0||
|18|Pin|24|PIO_PA18X1_AFE0_AD1|PIO_INPUT|ADC1||
|17|Pin|25|PIO_PA17X1_AFE0_AD0|PIO_INPUT|Ok Key||
|16|Pin|45|PIO_PA16C_PWML2|PIO_PERIPH_C|PWM_CH2||
|15|Pin|49|PIO_PA15B_TIOA1|PIO_PERIPH_B|||
|14|Pin|51|PIO_PA14A_SPCK|PIO_PERIPH_A|||
|13|Pin|42|PIO_PA13A_MOSI|PIO_PERIPH_A|||
|12|Pin|68|PIO_PA12A_MISO|PIO_PERIPH_A|||
|11|Pin|64|PIO_PA11A_NPCS0|PIO_PERIPH_A|||
|10|USB|66|PIO_PA10A_UTXD0|PIO_PERIPH_A|UTXD0 USB Din||
|9|USB|75|PIO_PA9A_URXD0|PIO_PERIPH_A|URXD0 USB Dout||
|8|Pin|36|PIO_PA8|PIO_OUTPUT_0|||
|7|Pin|35|PIO_PA7|PIO_OUTPUT_0|||
|6|Pin|114|PIO_PA6C_UTXD1|PIO_PERIPH_C|||
|5|Pin|73|PIO_PA5C_URXD1|PIO_PERIPH_C|||
|4|Pin|77|PIO_PA4A_TWCK0|PIO_PERIPH_A|||
|3|Pin|91|PIO_PA3A_TWD0|PIO_PERIPH_A|||
|2|Pin|93|PIO_PA2|PIO_OUTPUT_0|||
|1|Pin|99|PIO_PA1|PIO_OUTPUT_0|||
|0|Pin|102|PIO_PA0B_TIOA0|PIO_PERIPH_B|

# motor controllers (supplied info):

Z Motor:

|Function|Pin|SAM PIN|
|---|---|---|
|step|3|120|
|direction|44|119|
|enable|2|121|

Y motor:

|Function|Pin|SAM PIN|
|---|---|---|
|step|3|125|
|direction|44|7|
|enable|2|124|

X Motor:

|Function|Pin|SAM PIN|
|---|---|---|
|step|3|128|
|direction|44|126|
|enable|2|127|

E1 Motor:

|Function|Pin|SAM PIN|
|---|---|---|
|step|3|78|
|direction|44|74|
|enable|2|76|

# Screen:
```
16x4 winstar screen
```


# Connectors:

## J11
 * 51 pin
 * Manufacturer: Molex
 * Manufacturer Part No: 503908-5100
 * mouser link: https://www.mouser.de/ProductDetail/Molex/503908-5100?qs=%2Fha2pyFaduhUZ0D3%252Bx9QZ%2F9yiKVPFvryM3AFBkGfjdB5lJl2zWGmyA==


# Hacking Board
board containing the connector footprints for the 51, 22, and 16 pin ffp/fcp connectors: https://aisler.net/p/RWKQVPED . not yet verified.

# Warning
Be careful if power on after wipe the FW, the extruder is on and heating without any control, you better disconnect it
