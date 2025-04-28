# STARLINK For GAZA: Performance Evaluation Using Systems Tool kit Simulator STK

## Introduction
<p align="justify">
This project explores the dynamic landscape of satellite communication, focusing on the distinctive challenges presented by the Gaza Strip, where the infrastructure supporting wireless communications has been severely damaged due to ongoing conflict and bombings by Israeli forces. With the region's communication systems in disarray, there is a critical need for reliable connectivity solutions. This study investigates the transformative potential of SpaceX's Starlink satellite constellation to address these issues. Utilizing the Systems Toolkit Simulator (STK), we meticulously design and simulate satellite communication scenarios, evaluating crucial parameters to enhance connectivity. Our project reflects on the potential impact of integrating Starlink into Gaza's communication infrastructure, envisioning a future where satellite technology plays a pivotal role in overcoming communication barriers and supporting humanitarian efforts.
</p>

## Requirements and Methodology
<p align="justify">
The project focuses on the performance evaluation of coverage and data rates at ground receiver stations (Downlink Receivers) for Starlink communication satellites. The specific tasks and directives include: </p>
1) Use starlink tracking tool to pick any Starlink communication satellites. The tracking tool can be found via this link: https://satellitemap.space/</p>
~We must point out that Starlink satellites operate at three inclination angles (43°, 53°, and 97°). The lower the inclination, the more frequent the satellite passes above the target (Gaza Strip). Therefore, we will choose the satellites with 43° inclination to guarantee more coverage time.</p>
2) Set the home location to any location in Gaza Strip.</p>
~In our case, we picked the home location to be at 31°30'00.0"N 34°28'00.1"E in Gaza.</p>
3) Pick any communication satellites and write down its numbers then Check when will be the next pass for each satellite above Gaza.</p>
~Using the starlink tracking tool we picked 20 satellite in 2 different low earth orbits (LEO), the ID numbers of the satellite, the altitude and the next pass of each satellite are shown in the table below:</p>

| NO. | Satellite Number | Next Pass Time | Altitude (Km) |
|-----|------------------|----------------|---------------|
| 1 | STARLINK-30300 | 29-12-2023 04:09:40 | 570.9 |
| 2 | STARLINK-30335 | 29-12-2023 04:19:43 | 565.2 |
| 3 | STARLINK-30338 | 29-12-2023 03:45:06 | 561.2 |
| 4 | STARLINK-30349 | 29-12-2023 03:54:47 | 570.9 |
| 5 | STARLINK-5084 | 29-12-2023 04:31:31 | 565.2 |
| 6 | STARLINK-5359 | 29-12-2023 10:18:11 | 561.2 |
| 7 | STARLINK-5390 | 29-12-2023 04:43:34 | 570.9 |
| 8 | STARLINK-5401 | 29-12-2023 04:55:48 | 565.2 |
| 9 | STARLINK-5402 | 29-12-2023 10:11:38 | 561.2 |
| 10 | STARLINK-5407 | 29-12-2023 04:01:23 | 570.9 |
| 11 | STARLINK-5492 | 28-12-2023 16:52:26 | 565.2 |
| 12 | STARLINK-5493 | 28-12-2023 16:43:58 | 561.2 |
| 13 | STARLINK-5627 | 28-12-2023 17:02:53 | 570.9 |
| 14 | STARLINK-5647 | 28-12-2023 22:19:11 | 565.2 |
| 15 | STARLINK-5649 | 28-12-2023 22:28:58 | 561.2 |
| 16 | STARLINK-5658 | 28-12-2023 16:35:29 | 570.9 |
| 17 | STARLINK-5661 | 28-12-2023 16:13:47 | 565.2 |
| 18 | STARLINK-5663 | 28-12-2023 22:37:12 | 561.2 |
| 19 | STARLINK-5666 | 28-12-2023 16:00:44 | 570.9 |
| 20 | STARLINK-5675 | 28-12-2023 16:23:44 | 565.2 |
</p>
- Note: The default time for our project starts at 28 Dec 2023 12:00 PM
<p align="justify">
4) Knowing the satellite altitude, calculate the semi major access (radius), the orbiting period and the orbiting velocity for the satellites knowing that the mass of the satellite is 500Kg.</p>
~The results are tabulated in the table below

| NO. | Satellite Number | Altitude (Km) | Semi Major Axis (Km) | Orbiting Period (min) | Orbiting Velocity (rad/sec) |
|-----|------------------|----------------|---------------|----------------|---------------|
| 1 |	STARLINK-30300|	570.9|	6937.20947|	95.83781|	0.001092676|
| 2 |	STARLINK-30335|	565.2|	6937.21094|	95.83784|	0.001092676|
| 3 |	STARLINK-30338|	561.2|	6937.20474|	95.83771|	0.001092677|
| 4 |	STARLINK-30349|	568|	6937.21586|	95.83794|	0.001092675|
| 5 |	STARLINK-5084|	559.4|	6937.25464|	95.83875|	0.001092666|
| 6 |	STARLINK-5359	|563.7|	6937.22492|	95.83813|	0.001092673|
| 7 |	STARLINK-5390|	559.2|	6937.31531|	95.84|	0.001092651|
| 8 |	STARLINK-5401	|561.5|	6937.22635|	95.83816|	0.001092672|
| 9 |	STARLINK-5402	|559.4|	6937.22995|	95.83824|	0.001092671|
| 10 |	STARLINK-5407|	570.7|	6937.23016|	95.83824|	0.001092671|
| 11 |	STARLINK-5492	|566.6|	6937.21073|	95.83784|	0.001092676|
| 12 |	STARLINK-5493|	561.3|	6937.32928|	95.84029|	0.001092648|
| 13 |	STARLINK-5627	|570.8|	6937.22331|	95.8381|	0.001092673|
| 14 |	STARLINK-5647	|569.2|	6937.20737|	95.83777|	0.001092677|
| 15 |	STARLINK-5649	|559.9|	6937.20817|	95.83778|	0.001092677|
| 16 |	STARLINK-5658	|558.2|	6937.23717|	95.83839|	0.00109267|
| 17 |	STARLINK-5661	|563|	6937.20935|	95.83781|	0.001092676|
| 18 |	STARLINK-5663	|558.3|	6937.18772|	95.83736|	0.001092681|
| 19 |	STARLINK-5666	|560.3|	6937.16618|	95.83691|	0.001092686|
| 20 |	STARLINK-5675	|560.9|	6937.18973|	95.8374|	0.001092681|
<p align="justify">
-The previous results were evaluated using the Two Line Element (TLE) data for each satellite and the equations from reference [1] as shown below:</p>

<p align="center">  
$\Large n_{\frac{r a d}{s e c}}=\frac{2 \pi}{24 * 60 * 60} n_{\frac{r e v}{d a y}}$
<p align="center"> 
$\Large P_{\min }=\frac{2 \pi}{n_{\frac{r a d}{\min }}}$
<p align="center"> 
$\Large a=\sqrt[3]{\frac{\mu}{n^2}} \quad$ „, where $\mu=3.986005 * 10^{14} \frac{m^3}{\mathrm{~s}}$
<p align="center"> 
$\Large V=\frac{2 \pi}{P_s}$
<p align="justify">
Where n, a, V, μ, P  represent the mean motion, semi-major axis, velocity (in km/s), Earth's geocentric gravitational constant, and orbital period, respectively.

##  Design Overview & Objectives
### Overview
<p align="justify">
As we immerse ourselves in the Simulation Design phase, primed to breathe life into our three scenarios, several key pieces of information and constraints merit careful consideration:<p align="justify">
1) <b>Satellite Orbits Visualization:</b> The orbital paths of the selected satellites are meticulously depicted in both 2D and 3D graphics, as illustrated in The figures below. Notably, the orbits exhibit a unique shape, with uniformly changing Right Ascension of Ascending Nodes (RAAN) angles. This characteristic ensures that the coverage remains consistent over extended periods, with satellites providing approximately 23 hours (nearly 97%) of coverage per day.

<p align="center">
  <img src="Images/STK 2D Graphic.png" alt="STK 2D Graphic" width="800">
  <img src="Images/STK 3D Graphic.png" alt="STK 3D Graphic" width="800">
</p>

<p align="justify">   
2) <b>Operational Frequency and Modulation:</b> Aligning with Starlink standards, our project adopts a serious approach by adhering to the frequency bands and modulation techniques outlined in the table below. For downlink transmission, we employ a frequency of 12GHz and OQPSK modulation, while uplink transmission utilizes 14.2GHz and BPSK modulation. The selected data rate stands at 100 Mbps, acknowledging the variability in Starlink service, ranging from 50 Mbps to 150 Mbps, with latency spanning 20 ms to 40 ms.

| Characteristic|	Uplink |	Downlink |
|---------------|--------|-----------|
| Frequency (GHz) |14.0 - 14.5 |	10.7 - 12.7|
| Frequency (GHz) |27.5 - 29.1	 | 17.8 - 18.6|
| Frequency (GHz) |29.5 - 30.0	 | 18.8 - 19.3|
| Frequency (GHz)  |47.2 - 52.4	 |  37.5 - 42.5|               
|Modulation Type	| BPSK, QAM |	OQPSK, QAM|

<p align="justify">
3) <b>Receiver G/T and Transmitter EIRP:</b> The project maintains signal integrity with a Ground-to-Noise Temperature (G/T) ratio of 9 dB/K for the receiver and an Effective Isotropic Radiated Power (EIRP) of 30 dBW for the transmitter, in line with Starlink's specifications as detailed in the table below. 

|Characteristic |	User Beam |
|---------------|-----------|
|G/T (dB/K) |	8.7 - 9.8|
|EIRP (dBW) |	0 - 39.44|


<p align="justify">
4) <b>Antenna Design:</b> We Employing a parabolic antenna for the ground station, the design carefully considers the balance between antenna diameter and Bit Error Rate (BER), recognizing the impact on data transmission quality based on the operational frequency. Elevating our design, the satellites feature a sophisticated phased array antenna, allowing dynamic control over the radiation beam. This innovation enables beam steering and power efficiency, surpassing traditional tracking antenna capabilities. Refer to figure below from Systems Tool Kit (STK) for insights into the bent radiation beam based on satellite position. 

<p align="center">
  <img src="Images/Antenna Beam Steering.png" alt="STK 2D Graphic" width="500">
</p>

### Project Objectives
<p align="justify">
The project's overarching objectives center on establishing a robust and enduring satellite communication infrastructure for the Gaza Strip. With a primary focus on providing extended coverage of at least 23 hours per day, the initiative seeks to deliver a reliable connection that caters to the critical missions of hospitals and humanitarian organizations. Concurrently, the project aims to analyze and optimize key performance metrics, including the variation of Eb/N0 and BER over time for each satellite in the constellation. Strategies for improvement encompass exploring advancements such as phased array antennas, evaluating their impact on beam steering, and assessing their potential to enhance power efficiency. Beyond technological considerations, the project aspires to gauge the real-world impact of these advancements on healthcare and humanitarian operations in the region. The comprehensive documentation of methodologies, results, and recommendations further underscores the commitment to advancing satellite communication capabilities in challenging environments.
</p>

## Project Scenarios & Results
### First Scenario:
- Insert the satellites that you picked using the tracking tool and define a facility in Gaza Strip to be the receiver.</p>
- For each satellite add a sensor with 40 degrees field of view.</p>
- For each satellite add downlink transmitter and uplink receiver.</p>
- Add uplink transmitter and downlink receiver for the ground station (facility in Gaza Strip).</p>
- Define antenna and link it with the previously defined transmitters and receivers.</p>
- Run the simulation and generate the access report for each satellite out of all the satellites and detect which one has the largest access period.</p>
- Generate a graph showing the variation of Eb/N0 with time.</p>
- Generate a graph showing the variation of BER with time.</p>
~<b>Results</b>
<p align="justify">
After we defined the transmitting and receiving antennas for each satellite and ground station. To enhance the simulation's accuracy, a sensor was added for each satellite, ensuring a comprehensive representation of the communication system's behavior. Then we generate an access report and show that the Starlink-5359 satellite has the largest access period as shown in figure below.
<p align="center">
  <img src="Images/Starlink-5359 Access Report.png" alt="Starlink-5359 Access Report" width="800">
</p>
Then we generate a graph showing the variation of the Eb/N0 with time and BER with time for Starlink-5675 Satellite.
<p align="center">
  <img src="Images/EbN0 Without Tracking.png" alt="EbN0 Without Tracking" width="800">
</p>
<p align="center">
  <img src="Images/BER Without Tracking.png" alt="BER Without Tracking" width="800">
</p>

### Second Scenario
- Do the same again for the steps in the first scenario but now using motorized tracking ground station antenna.</p>
- Discuss how the motorized ground station antenna improve the connection.</p>
~<b>Results</b>
<p align="justify">
In the preceding Scenario, the outcomes indicate that Eb/N0 and BER values exhibit optimal performance exclusively when the satellite aligns directly above Gaza, denoted by an elevation angle of 90 degrees. However, this configuration proves insufficient for a robust communication system, given our project's emphasis on achieving reliable and extended coverage. To address this challenge, the second scenario introduces a strategic solution—incorporating a motorized servo motor as show in the figure below.

<p align="center">
  <img src="Images/Tracking a Satellite.png" alt="BTracking a Satellite" width="800">
</p>
<p align="justify">
This addition enables the ground receiver antenna to dynamically track and align itself with the transmitted signal from the satellite antenna. Implemented in Systems Tool Kit (STK), this process involves defining a sensor within the ground station and linking it to the receiver, ensuring the desired tracking capability for enhanced communication performance.

<p align="justify">
After that we generate a graph showing the variation of the Eb/N0 with time and BER with time for the same previous satellite (Starlink-5675 Satellite).

<p align="center">
  <img src="Images/EbN0 With Tracking.png" alt="EbN0 With Tracking" width="800">
</p>
<p align="center">
  <img src="Images/BER With Tracking.png" alt="BER With Tracking" width="800">
</p>

<p align="justify">
- Note: In first scenario the EIRP was 60 dBW but for the second scenario it is 30 dBW as in practical value.
<p align="justify">
The preceding figure vividly illustrates the substantial improvement in Eb/N0 and BER resulting from the implementation of a motorized tracking receiver. Remarkably, despite the energy in the first scenario being 1000 times greater than that in the second scenario, the performance exhibited marked enhancement. This highlights the effectiveness of motorized tracking in optimizing communication outcomes, showcasing superior performance even in scenarios with lower energy inputs.

### Third Scenario
- Knowing that there is another nearby starlink satellite that transmit to the same ground station using the same frequency, evaluate the interference that may be caused and discuss how to eliminate it.</p>
- Document all the results and discuss how efficient the system is and what we can do to increase the efficiency for the system.</p>
~<b>Results</b>
<p align="justify">
In the preceding scenarios, we observed effective strategies for enhancing Eb/N0 and BER. However, let's consider a hypothetical scenario where someone, like the Israeli occupation, opposes the provision of this service and initiates deliberate jamming and interference with the Starlink network on a nearby frequency. To tackle this challenge, the third scenario unfolds, introducing a solution to counteract interference. In this scenario, we will design filters to minimize interference, ensuring the preservation of a reliable communication network despite external attempts to disrupt it.
<p align="justify">
To simplify the scenario, let's assume that the jamming signal originates from the transmitter on the same Starlink satellite, with a center frequency of 12.25GHz. Additionally, we enhance the realism of the situation by enabling the Power Spectral Density (PSD) option for the transmitters. Subsequently, we evaluate the impact on the Bit Error Rate (BER) and Carrier-to-Noise ratio (C/N), introducing a more nuanced perspective to address potential interference challenges. The figures down below show the results.

<p align="center">
  <img src="Images/Link Information Without Filter.png" alt="Link Information Without Filter" width="800">
</p>
<p align="center">
  <img src="Images/carrier to noise without filter.png" alt="carrier to noise without filter" width="800">
</p>

<p align="justify">
The previous figures show the difference between the BER & BER+I. Note how the interference affect the connection reliability and the BER become worse and high than the acceptable value. Also, Note how much the SNR affected by the interference.
<p align="justify">
To overcome this problem, we design a filter for both transmitter and receiver. The purpose of designing the filter of former to concern the power at the center frequency and of latter to extract only the wanted band from the signal. For this project we Design a Butterworth filter for the receiver and the next figure shows the frequency response of the filter.

<p align="center">
  <img src="Images/Rx Butterworth Filter.png" alt="Rx Butterworth Filter" width="800">
</p>
For the transmitters the filter type also Butterworth but with small order value and figure below illustrate its frequency response.

<p align="center">
  <img src="Images/Tx Butterworth Filter.png" alt="Tx Butterworth Filter" width="800">
</p>
After we apply the filters, we expect to isolate and minimize the interference so now we will run the simulation and observe the outputs.

<p align="center">
  <img src="Images/Link Information with Filter.png" alt="Link Information with Filter" width="800">
</p>
<p align="center">
  <img src="Images/carrier to noise with filter.png" alt="carrier to noise with filter" width="800">
</p>
<p align="justify">
The implementation of filters plays a pivotal role in mitigating interference and elevating communication reliability. These filters effectively suppress the unwanted jamming signal by strategically attenuating the undesired frequency components, the filters create a cleaner signal environment for the communication system. This refined signal quality translates into a noticeable improvement in communication reliability, as reflected in enhanced Bit Error Rate (BER) and Carrier-to-Noise ratio (C/N). The filters act as a crucial defense mechanism, fortifying the integrity of the communication network against external interference and ensuring a robust and dependable connectivity experience.

### Summary
<p align="justify">
The three scenarios implemented in this project have significantly enhanced communication outcomes. The initial scenario laid the foundation, demonstrating optimal performance when the satellite was directly above Gaza. The introduction of a motorized tracking receiver in the second scenario showcased remarkable improvements, overcoming limitations observed in the first scenario. Finally, the third scenario addressed external interference by designing filters, leading to a substantial boost in communication reliability. 

## Conclusion
<p align="justify">
In conclusion, the STARLINK FOR GAZA project employs the Systems Toolkit Simulator (STK) to evaluate the feasibility of satellite communication in Gaza, aiming to build a robust communication infrastructure. The project progresses through three simulation scenarios, each addressing specific challenges: the first establishes a baseline with optimal performance when the satellite is directly overhead, the second enhances performance using a motorized tracking receiver to dynamically align with the satellite signal, and the third mitigates deliberate jamming with specialized filters. These strategies significantly improve communication reliability and coverage, showcasing the transformative potential of advanced technologies like motorized tracking and interference filters. The project underscores the importance of reliable satellite communication for healthcare and humanitarian operations in Gaza, reflecting a commitment to overcoming technical challenges and enhancing connectivity in challenging environments. Comprehensive documentation of methodologies, results, and recommendations further contributes to the advancement of satellite communication capabilities for the region.

## Simulation Files & Permission

The simulation files are available in this public repository and are free to use without needing permission. If you have any questions, feel free to email me at [mohammad.asaslih@gmail.com](mailto:mohammad.asaslih@gmail.com), and I will do my best to assist you.

## Creators

This project Created by Mohammad Ib. Al-Asaslih. No other individuals contributed to the creation or development of this work.

### Contact Information

- **Mohammad Ib. Al-Asaslih**  
  Email: [mohammad.asaslih@gmail.com](mailto:mohammad.asaslih@gmail.com)  
  Phone: +962-78-250-9494

## References
1. Roddy, D., Jones, W.L. and Long, D.G. (2024) Satellite Communications Dennis Roddy, W. Linwood Jones, David G. Long. New York: McGraw Hill. 
