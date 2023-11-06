# CrazyTempMonitor
Code to read temp, send to airtable &amp; adafruit, detect color, and control displays

Specifically, this is code to complete these tasks: 
1. Display a physical output of the temperature (LEDs in different weather conditions)
2. Pushes the temperature reading to an Adafruit dashboard every 5 min USING their MQTT broker
3. Uses a i2c device (Adadfruit gamepad with seesaw) to control the leds 
4. Changes from F to C or C to F (on the Adafruit dashbaord) depending on what color you hold in front of your computer's camera
    1. Note that you will need to write a Python code on the PC (Mu or Thonny or…) that uses reads the airtable cell and uses MQTT to update your Adafruit dashboard.
    2. Your Pico should also read the airtable cell with RestAPI and change something on your display accordingly. The Pico should also update Adafruit with the latest reading.
    - You have PyScript identify the color of the biggest blob in the image (is it red, green, or blue - or you can play with harder colors like purple if you want).
    - When you run the code on your machine, it should take the snapped image, find the color and send it to [Airtable](https://www.airtable.com/) (you will have to create a free account, make a database, and then figure out their API - check [here](https://airtable.com/developers/web/api/introduction) for help - if you scroll down, you can see a list of your databases - click on it and it will show you everything you need to get the API going - you do not even need their python library - do not forget to go [here](https://airtable.com/create/tokens) to get an access token)
    - A python program on your computer and Pico should then read the airtable entry and the PC should send it over MQTT to Adafruit.
  

Make sure to download all the necessary libraries like MQTT and i2c. 
