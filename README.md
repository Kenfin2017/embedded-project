# temp-humidity-2016
Arduino temperature and humidity first project

There are two sub project: 
•	I2C scanner 
•	Weather station

Before compiling the ”weather_station” sketch to Arduino, use ”i2c_scanner” project to retreive the address of the I2C bus interface while connecting expansion board on 
 then replace the found address to the following line in Weather_station sketch: 
LiquidCrystal_I2C lcd([address], 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE);

Then compile the codes in Weather_station and test the product.