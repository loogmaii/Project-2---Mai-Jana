![weather.png](https://github.com/loogmaii/Project_2_Mai_Jana/blob/main/pooooh.gif)

# Unit 2: A Distributed Weather Station for ISAK

## Criteria A: Planning

## Problem definition

It is December in UWC ISAK and Malcolm-San is starting to feel cold and sick. He suspects that the reason behind his cold is the change of humidity on campus. The reason behind his suspicion is that high humidity promotes the growth of mold which can cause respiratory issues [^1]. For that reason, he went to discuss with Mim-san who in fact denied his suspicions and said that it was just because his body is not adapting fast enough, since he is from Africa. To prove his point, he asked Jana and Mai to measure the temperature and humidity both inside and outside of the residences to store all the data in a graph - for everyone to be able to understand whether the humidity and temperature levels are healthy for the human body or not. From the results, it would be able to either confirm his suspicions or deny them. Finally, his last request is for them to make a poster to print out and hang up throughout the school.

## Rationale for Proposed Solution

Considering the client requirements an adequate solution includes a low cost sensing device for humidity and temperature and a custom data script that process and anaysis the samples acquired. For a low cost sensing device an adequate alternative is the DHT11 sensor[^2] which is offered online for less than 5 USD and provides adequare precision and range for the client requirements (Temperature Range: 0°C to 50°C, Humidity Range: 20% to 90%). Similar devices such as the DHT22, AHT20 or the AM2301B [^3] have higher specifications, however the DHT11 uses a simple serial communication (SPI) rather than more eleborated protocols such as the I2C used by the alternatives. For the range, precision and accuracy required in this applicaiton the DHT11 provides the best compromise. Connecting the DHT11 sensor to a computer requires a device that provides a Serial Port communication. A cheap and often used alternative for prototyping is the Arduino UNO microcontroller [^4]. "Arduino is an open-source electronics platform based on easy-to-use hardware and software"[^5]. In additon to the low cost of the Arduino (< 6USD), this devide is programable and expandable[^2]. Other alternatives include diffeerent versions of the original Arduino but their size and price make them a less adequate solution.

Considering the budgetary constrains of the client and the hardware requirements, the software tool that I proposed for this solution is Python. Python is open source, it is mature and supported in mutiple platforms (platform-independent) including macOS, Windows, Linux and can also be used to program the Arduino microprocessor [^6]. In comparison to the alternative C or C++, which share similar features, Python is a High level programming language (HLL) with high abstraction [^8]. For example, memory management is automatic in Python whereas it is responsability of the C/C++ developer to allocate and free up memory [^8], this could result in faster applications but also memory problems. In addition a HLL language will allow me and future developers extend the solution or solve issues proptly.  

It will take 2 weeks to make and will be evaluated according to the criteria A, B and C.  

## Design statement

In order to inform the client whether the temperature and humidity levels are at a healthy level or not, this project aims to develop a low-cost weather station that measures the values inside a dorm room (locally) and outside the house (remotely). It will also display a prediction for the next 12 hours for both temperature and humidity. To make the data easier for the client to understand, mathematical modeling will be used to visualize the data.



[^1]:American Lung Association. “Mold and Dampness.” Lung.org, 2022, www.lung.org/clean-air/at-home/indoor-air-pollutants/mold-and-dampness. Accessed 12 Dec. 2022.
[^2]: Industries, Adafruit. “DHT11 Basic Temperature-Humidity Sensor + Extras.” Adafruit Industries Blog RSS, https://www.adafruit.com/product/386. 
[^3]: Nelson, Carter. “Modern Replacements for DHT11 and dht22 Sensors.” Adafruit Learning System, https://learn.adafruit.com/modern-replacements-for-dht11-dht22-sensors/what-are-better-alternatives.   
[^4]:“How to Connect dht11 Sensor with Arduino Uno.” Arduino Project Hub, https://create.arduino.cc/projecthub/pibots555/how-to-connect-dht11-sensor-with-arduino-uno-f4d239.  
[^5]:Team, The Arduino. “What Is Arduino?: Arduino Documentation.” Arduino Documentation | Arduino Documentation, https://docs.arduino.cc/learn/starting-guide/whats-arduino.  
[^6]:Tino. “Tino/PyFirmata: Python Interface for the Firmata (Http://Firmata.org/) Protocol. It Is Compliant with Firmata 2.1. Any Help with Updating to 2.2 Is Welcome. the Capability Query Is Implemented, but the Pin State Query Feature Not Yet.” GitHub, https://github.com/tino/pyFirmata. 
[^7]:Python Geeks. “Advantages of Python: Disadvantages of Python.” Python Geeks, 26 June 2021, https://pythongeeks.org/advantages-disadvantages-of-python/. 
[^8]: Real Python. “Python vs C++: Selecting the Right Tool for the Job.” Real Python, Real Python, 19 June 2021, https://realpython.com/python-vs-cpp/#memory-management. 

## Success Criteria

1. The solution provides a visual representation of the Humidity and Temperature values inside a dormitory (Local) and outside the house (Remote) for a period of minimum 48 hours. 
2. The solution provides a mathematical modelling for the Humidity and Temperature levels for each Local and Remote locations. ```(SL: linear model)```
3. The solution provides a comparative analysis for the Humidity and Temperature levels for each Local and Remote locations including mean, standad deviation, minimum, maximum, and median.
4. ```(SL)```The Local samples are stored in a csv file.
5. Create a prediction the subsequent 12 hours for both temperature and humidity.
6. A poster summarizing the visual representations, model and analysis is created and communicated.

# Criteria B: Design

## System Diagram **SL**

<img width="1312" alt="Screen Shot 2565-11-23 at 20 50 59" src="https://user-images.githubusercontent.com/111941936/203539941-27027bea-087c-42ac-acce-91a826433803.png">

**Fig.1** shows the system diagram for the proposed solution (**SL**). The indoor variables will be measured using an Arduino microprocessor and the sensor DHT11 conencted to the local computer (Laptop) located inside a room. The outdoor variables will be requested to the remote server using a GET request to the API of the server at ```192.168.6.147/readings```. The local values are stored in a CSV database locally.

## List of Materials

1. Arduino microprocessor x 1
2. Sensor DHT11 x 1
3. Computer x 1
4. Extension chord x 1



## Record of Tasks
| **Task No** | **Planned Action**                                                                  | **Planned Outcome**                                                                                                                    | **Time estimate** | **Target completion date** | **Criterion** |
|-------------|-------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|-------------------|----------------------------|---------------|
| 1           | Write the Problem context                                                           | Identify the audience and their problem                                                                                                | 20 min            | Nov 22                     | A             |
| 2           | Create success criteria                                                             | Ensure the final product satisfies client's needs                                                                                      | 10 min            | Nov 23                     | A             |
| 3           | Write design statement                                                              | Create a mutual understanding between team members and client                                                                          | 10 min            | Nov 23                     | A             |
| 4           | Write proposed solution                                                             | Recieve feedback and approval to continue development of product                                                                       | 10 min            | Nov 24                     | B             |
| 5           | List materials needed                                                               | Establish understanding of materials needed for the product to function and have a better understanding of the system diagram          | 10 min            | Nov 24                     | A             |
| 6           | Collect materials and sign scope of work                                            | Obtain all the supplies required to build a weather station in the dorm and sign them out with the aim of only doing so for the client | 10 min            | Nov 24                     | A             |
| 7           | Download necessary libraries and applications                                       | Prepare the computer to accept data from the sensor and to perform upcoming coding                                                     | 20 min            | Nov 24                     | B             |
| 8           | Import necessary libraries into Python files                                        | For the code to be able to receive and process the data into the final product                                                         | 15 min            | Nov 25                     | B             |
| 9           | Set up the materials to the computer inside the room                                | Have the Arduino and computer ready to record required data every 5 minutes for 48 hours                                               | 20 min            | Nov 25                     | B             |
| 10          | Connect to the Arduino microprocessor                                               | To be able to receive temperature and humidity data from the sensor DHT11                                                              | 10 min            | Nov 25                     | C             |
| 11          | Create code to take temperature and humidity data from the sensor DHT11             | Receive data that would later on be used for comparing outside and inside temperature and humidity                                     | 60 min            | Nov 26                     | C             |
| 12          | Write code to save temperature, humidity, date and time information in the CSV file | Humidity, temperature, date and time data are saved to designated CSV files every 5 minutes, ready to be proccesed into a graph        | 60 min            | Nov 26                     | C             |
| 13          | Produce MVP (minimal viable product 'prototype')                                    | Provide client with general idea of what the product will look like                                                                    | 20 min            | Nov 26                     | C             |
| 14          | Film MVP to show to client                                                          | A clear video that provides the client with a clear idea of what the product will look like                                            | 20 min            | Nov 26                     | C             |
| 15          | Run code for 48 hours to collect temperature and humidity data in R3-10 room A      | Obtain 48 hours of 5-minute approximate temperature and humidity data from R3-10A.                                                     | 48 hours          | Nov 27                     | C             |

## Test Plan
| **Software Test Type**              | **Input**                                                                                                                             | **Process**                                                                                                       | **Output**                                                                                                                                            |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| Functional: Unit Testing            | Code to receive information of humidity and temperature from DHT sensor and store in CSV file in a format that is ready to be graphed | 1. Run the code  2. Leave to run for 48 hours 3. Frequently check the CSV file to ensure the data is being stored | The program is still continuously operating and collecting humidity and temperature data without any glitches or lags, and all data is up to current. |
| Functional: Integration Testing     |                                                                                                                                       |                                                                                                                   |                                                                                                                                                       |
| Functional: System Testing          |                                                                                                                                       |                                                                                                                   |                                                                                                                                                       |
| Non-Functional: Performance Testing |                                                                                                                                       |                                                                                                                   |                                                                                                                                                       |
| Non-Functional: Usability Testing   |                                                                                                                                       |                                                                                                                   |                                                                                                                                                       |

# Criteria C: Development

## List of techniques used

## Development
## MVP (minimal viable product 'prototype')
https://drive.google.com/file/d/1CdZhVE7wxouNFcLqTq6FZ73z6bevApU4/view?usp=share_link
# Criteria D: Functionality

A 7 min video demonstrating the proposed solution with narration
