# Design and Validation of an IoT System for an Experimental Laboratory Microgrid
## Jonathan Gómez, Juan M. Rey, Natalia Duarte, Iván Hernández, Maria A. Mantilla and Oscar Quiroga

_**Abstract:** In the energy transition context, electrical microgrids facilitate the integration of renewable generation into the electrical grid, improving the electrical system's reliability and accelerating its decarbonization. However, to promote the technological advancement of these grids, it is necessary to develop tools to validate new technologies and solutions, such as using the Internet of Things (IoT) for their operation and control. This work presents the design, implementation, and validation of an IoT system for an experimental laboratory microgrid developed at Universidad Industrial de Santander. The main design phases of the IoT system are described, beginning with the definition of requirements and extending through the component selection. Validation tests are proposed to verify the functionalities of the IoT system. The results demonstrate that the IoT system successfully enables the transmission and reception of data from external users and servers. The reported experience and the proposed validation tests are relevant for researchers interested in implementing IoT-based stages in existing or future laboratory microgrids_ 

![Graphical abstract](/Figures/Graphical_Abstract2.png)

## Tests
**Test 1: Receiving and sending data from the local communications server.**
The first test starts by validating the server's communication capacity with other devices. The circuit designed for this test incorporates a resistive divider implemented with a monitored potentiometer. The information is then collected from the communications server and sent to another controller board, which activates an LED based on a preset threshold.
<div id="header" align="center">
  <img src="/Tests/Prueba1.png" width="400"/>
</div>

**Test 2: Bidirectional communication validation.**
The next test consists of validating the bidirectional exchange of information between the local server and the controller boards. For this, voltage value data is sent from the server to controller board, which set this voltage in a DAC outputs. This output is connected to an ADC input of the same controller board and the data is sent back to the local server. Then, the data is displayed in an interface.
<div id="header" align="center">
  <img src="/Tests/Prueba2.png" width="400"/>
</div>

**Test 3: Testing the interaction with the local user.**
The following test seeks to validate the implementation of dynamic control actions by a local user through an interface. For this, the user can establish voltage values for each control board, each of which will have a pin of an RGB LED connected to one of its DAC outputs. Each color is associated with a board: the first controls the color red, the second controls the color green, and the third controls the color blue. Once the user changes the voltage signals associated with each card and, therefore, each color, it is possible to observe the operation of the local communications system visually.
<div id="header" align="center">
  <img src="/Tests/Prueba3.png" width="400"/>
</div>

**Test 4: Testing the system’s flexibility.**
This test consists of receiving data from two control boards, performing a mathematical operation with them and, based on the result, performing a control action on a third controller board. For the particular case, two control boards collect voltage data from a DC source. These values are sent to the server. Finally, the result of the operation is compared with a predefined or dynamic threshold, and according to what is obtained, an LED connected to a third control card is turned on.
<div id="header" align="center">
  <img src="/Tests/Prueba4.png" width="400"/>
</div>

**Test 5: Validation of variable exchange (workflow).**
In the following test, data is sent and received from the devices simultaneously to recreate a real workflow situation. For this, input data from each control card will be collected while its available outputs are activated. The diagram in the figure describes the data acquisition from resistive dividers connected to each control board. The value of this data is compared to a threshold and used to activate an LED on the other control board.
<div id="header" align="center">
  <img src="/Tests/Prueba5.png" width="400"/>
</div>

**Test 6: Publishing and subscribing data from an MQTT server.**
In this test the controller boards are used to collect data from resistive dividers, which is published to a web server. Subscribing to this information from the MQTT server, activates some of its front LEDs (located in the hardware) associated with each control board, and a third LED associated with the sum of the voltages with respect to a preset threshold.
<div id="header" align="center">
  <img src="/Tests/Prueba6.png" width="400"/>
</div>

**Test 7: Testing interaction with an external user.**
Once the operation of the MQTT server has been confirmed, a complete validation of the IoT system is proposed. For this, a remote user is enabled to visualize the collected data and perform actions on the devices defined for this purpose. The diagram for this validation consists of two stages. The first is similar to test 3, with an RGB LED connected through its pins to the three DAC ports of the three control boards. These boards will receive the action signals from the MQTT server to be applied to the DAC outputs controlling each color. On the other hand, from the same interface, the user can turn on or turn off the front LEDs of a PLC, simulating the activation of peripherals connected to the microgrid.
<div id="header" align="center">
  <img src="/Tests/Prueba7.png" width="400"/>
</div>

**Test 8: Validation on the complete system.**
Finally, once the operation of all the elements of the IoT system has been verified, a test using the power stage of the experimental laboratory microgrid is proposed. A controller board is used to control a power inverter and its data is published by the local server to a web server, from where the interface developed for data visualization is linked. 
<div id="header" align="center">
  <img src="/Tests/Prueba8.png" width="400"/>
</div>
