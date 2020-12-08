# LTT: Effect of Stacking Radiators on Water Temperature
Determine the effectiveness of stacking multiple radiators as a cooling solution using various statistical tests

*Note: Raw datasets are not uploaded for confidentiality reasons.*

## Problem
[Linus Tech Tips](https://www.youtube.com/user/LinusTechTips) did a [video](https://www.youtube.com/watch?v=vauAJl29xlw) about an experiment where they took measurements of air temperatures at the inlet and outlet of radiators in an enclosed wind tunnel. LTT’s experiment attempts to determine the effectiveness of stacking multiple radiators as a cooling solution for a water cooling loop with a CPU and GPU. LTT presented the data in the video exactly as they gathered it, without applying the techniques such as **LOESS** or **Kalman smoothing**, or without using statistical properties to determine the significance of their claims. In this project we seek to:
- Clean and smooth the data provided
- Learn about the relationship between stacking radiators on radiator exhaust temperature 
- See how many radiators is most optimal for thermal performance

## Dataset
Seven 240MM crossflow radiators from Alphacool were used to acquire raw data, with low profile fittings to stack those radiators together and 3D printed end caps for holding the radiators. Wind tunnel was snapped together from clear acrylic letting the air flow go between radiators. Two thermistor-type temperature probes were attached to each radiator to measure the temperature difference of water entering and exiting the radiator.

Collin from Linus Tech Tips created a data logging system which samples data from the sensors every 250 milliseconds (four times per sensor) with the help of Arduino code. The team then converts the resistance of the thermistor senator embedded in each of the radiators into Celsius degrees using the Steinhart-Hart Equation. Afterwards, they utilized trimpods to calibrate each sensor to a known temperature using a water bath. Once all the sensors are readings within 0.5o of each other, the data is pushed out via a serial connection to a computer running PuTTy which outputs all the data into a text file for later processing.

## Result

The conclusion shows that for a wind tunnel setup with stacked radiators and a similar hardware setup, if the radiators are arranged such that the hottest radiator gets air first, then 3 radiators is the most effective with minimal heat soak, while if the coldest radiator gets air first, then 2 radiators has the most impact, but it scales minimally with minimal heat soak 3 radiators onwards.

See [report](https://github.com/wendyhwl/LTT-Stacking-Radiators-Cooling/blob/main/report.pdf) for detailed data cleaning, smoothing processes.

## Contributors

Orion Hsu, Wendy Huang, Vincent Law

## References

[Video from Linus Tech Tips](https://www.youtube.com/watch?v=vauAJl29xlw)

