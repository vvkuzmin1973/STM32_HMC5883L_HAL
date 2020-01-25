# STM32_HMC5883L_HAL
This library for STM32 HAL is based on ARDUINO library: https://github.com/jarzebski/Arduino-HMC5883L

1. Change HMC5883L.h :

#define I2C hi2c2
to
#define I2C YOU_I2C_HAL_VARIABLE


Then everything is the same as in the Arduino library (only functions without a class and with the prefix HMC5883L):

2. Init :
  HMC5883L_setRange(HMC5883L_RANGE_1_3GA);
  HMC5883L_setMeasurementMode(HMC5883L_CONTINOUS);
  HMC5883L_setDataRate(HMC5883L_DATARATE_15HZ);
  HMC5883L_setSamples(HMC5883L_SAMPLES_1);
  HMC5883L_setOffset(0, 0);

3. To get the values :

	  Vector mag = HMC5883L_readRaw();
	  printf("%f %f %f\r\n",mag.XAxis,mag.YAxis,mag.ZAxis);
