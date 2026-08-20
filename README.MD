# README for Tad5242 Ultra Design Files

The files in this repository are the production and design files for a TAD5242-based small i2s DAC. 

## Board Specifications

The following images show measured specifications using a DSPi (Pico) system to create the I2S stream and a QuantAsylum QA403 to test the analog output.
![](SpecImage\QAImg_260820_063636.png)
![](SpecImage\QAImg_260820_063701.png)
![](SpecImage\QAImg_260820_063839.png)
![](SpecImage\QAImg_260820_063937.png)

## Design Decisions

Most of the board cost is in two chips, the TAD5242 DAC and the ADM7170 analog DC supply. The DC supply chip is a constraint on SNR. It is low noise yet affordable. The TAD5242 has
a large number of hardwired options, only one of which is available on the board - single-ended output.
The board uses two TRS miniplugs for stereo balanced output. Miniplugs can easily handle the low (2VRMS/47K load) output power requirements. If you prefer each output has a 3-terminal dupont pin output for other
connector types.

The board uses the factory recommended filter capacitor sizes, although the output circuit is a bit more complex 
than factory spec to improve capacitor tolerance fit. 

## Board Features

The TAD5242 is a high quality TI DAC chip. It supports a number of options (such as i2c control) that are not enabled on this specific board. The one available option is an SMD location for a resistor to switch the board to single-ended output. Even with that switch, blocking capacitors are recommended. The board also contains solder holes for two leaded blocking capacitors if you wish to do that.

The TAD5242 Ultra only has some of the DAC options available. By default the board is designed for balanced output, to be used with balanced amplifiers. 
It may be used unbalanced but the output voltage is 0 to 2V not -1V to 1V so nominally that requires a blocking capacitor. The board contains places to solder in two leaded blocking capacitors as well as a shorting location (RSNGL) to enable the single-ended mode of the TAD5242 chip.

## Board Production

The bill of materials is based on parts available at JLCPCB.
