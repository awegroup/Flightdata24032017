# Instrumented kite power system test flight on 24 March 2017

An updated version of this file is maintained on  https://github.com/rschmehl/wes2018

## Introduction
The objective of the test flight was to use a newly developed sensor rig for in situ measurement of the relative flow velocity, both magnitude and direction, at the kite [[1](#Oehler2017)]. The measurements were performed with the 100 kW technology development platform of Kitepower BV, a spin-off company from Delft University of Technology. For this particular test flight, the kite power system was equipped with a Leading Edge Inflatable (LEI) V3 kite with a total wing surface area of 25 m² and a projected area of 19.76 m². The mass of the wing was 11 kg, the mass of the suspended kite control unit (KCU) was 8.4 kg, the mass of the IMU and GPS sensors mounted on the center strut of the wing was 2.4 kg and the mass of the sensor rig for relative flow measurements was 1.0 kg. The traction force was transferred to the ground station by a tether made of Dyneema with a diameter of 4 mm and a line density of 0.013 kg/m. The ground station with 20 kW nominal traction power was used. More details of the configuration of the kite subsystems for this test and the use of the data for aerodynamic characterization of the kite are given in [[2](#Oehler2018b)]. A general description of the kite power system is given in [[3](#Vlugt2013)].

## Description of the test
The recorded test flight covers ten pumping cycles. Each cycle consists of a traction phase with roughly two figure of eight maneuvers and a retraction phase.
The three-dimensional flight path of a representative cycle is illustrated in [[1](#Oehleru_av_batt2017), p. 7]. The data recording starts with t = 0 s at the moment of
launching the kite, or, more precisely, the time (accuracy ∆t = 0.1 s) at which the ground station starts to reel in the tether, which triggers the kite to lift off. The ten pumping cycles with relevant measurement data cover the time range  between 1480 and 3230 s. All ten cycles have a similar altitude profile and flight
path. They start with the traction phase at a low altitude of around 120 to 250 m. During the retraction phase the kite first rises to a higher altitude of 300 to 430 m which and then drops again to lower altitude because of the retraction of the tether. In the time period between launch and 1480 s the kite was mainly parked at a high altitude to take care of some mechanical issues at the ground station.

The primary objective of the test was to measure the pitch and yaw components of the inflow angle plus the apparent wind speed. The magnitude of the relative flow velocity was measured with a Pitot tube, while the flow angles were measured by two orthogonal wind vanes. The relative flow sensor was mounted in the power lines, roughly nine meters below the wing and one meter above the KCU. The standard sensors of the kite power system were used to measure the pressure, temperature, position (GPS), and attitude (IMU) of the kite plus the tether force, reel out speed, and wind speed/direction at the ground station. The data was recorded at a frequency of 20 Hz. A more detailed description of the design, construction and calibration of the relative flow sensor is given in [[1](#Oehleru_av_batt2017), p. 25 ff]. The data has been used in a parallel study to validate a quasi-steady system model [[4](#JerezVenegas2017), p. 27 ff]. A similar measurement setup has been used to analyze the steering behavior of a kite [[5](#VanReijen2018a), [6](#Oehler2018a)].

The test flight was performed at the former airfield Valkenburg, close to Leiden, with the ground station positioned at a latitude of 52.1691°, a longitude of 4.4310° and an elevation of −5 m (below sea level).

## Content of the data set

The acquired data is provided in csv-format. In the content description we use the following abbreviations:
- KCU: Kite control unit, sometimes denoted also as control pod
- GS: Ground station
- NED: North-East-Down reference frame

<!--- descriptions and units reconstructed from ProcessData's Log.py --->

| ID | Variable      | Description   | Unit          |
| ----- | ------------- | ------------- |------------- |
|  0 |  `time` | time relative to launch | s |
|  1 | `date` | date | dd-mm-yyyy |
|  2 | `time_of_day` | time  | hh:mm:ss |
|  3 | `airspeed_temperature` | air temperature | °C |
|  4 | `airspeed_diff_pressure_filtered` | Pitot differential pressure  | Pa |
|  5 | `airspeed_diff_pressure_raw` | Pitot differential pressure raw | Pa |
|  6 | `airspeed_pressure` | barometric pressure | Pa |
|  7 | `airspeed_voltage_1` | voltage for sideslip angle | V |
|  8 | `airspeed_voltage_2` | voltage for vertical inflow angle | V |
|  9 | `airspeed_voltage_ref` | reference voltage | V |
| 10 | `lat_xsens` | Xsens latitude | deg |
| 11 | `long_xsens` | Xsens longitude | deg |
| 12 | `alt_xsens` | Xsens altitude | m |
| 13 | `lat_pixhawk` | Pixhawk latitude | deg |
| 14 | `long_pixhawk` | Pixhawk longitude | deg |
| 15 | `alt_pixhawk` | Pixhawk altitude | m |
| 16 | `phi_xsens` | Xsens roll | deg/s |
| 17 | `theta_xsens` | Xsens pitch | deg/s |
| 18 | `psi_xsens` | Xsens yaw | deg/s |
| 19 | `phi_pixhawk` | Pixhawk roll | deg/s |
| 20 | `theta_pixhawk` | Pixhawk pitch | deg/s |
| 21 | `psi_pixhawk` | Pixhawk yaw | deg/s |
| 22 | `d_phi` | Xsens delta azimuth angle | deg |
| 23 | `d_theta` | Xsens delta polar angle | deg  |
| 24 | `d_psi` | Xsens delta course angle | deg |
| 25 | `vx` | x(north)-velocity Xsens | m/s |
| 26 | `vy` | y(east)-velocity Xsens | m/s |
| 27 | `vz` | z(down)-velocity Xsens | m/s |
| 28 | `acc_x` | x(north)-acceleration Xsens | m/s² |
| 29 | `acc_y` | y(east)-acceleration Xsens | m/s² |
| 30 | `acc_z` | z(down)-acceleration Xsens | m/s² |
| 31 | `u_av_batt` | average voltage KCU battery (last 50 ms) | V  |
| 32 | `u_min_depower` | min. battery voltage depower motor controller (last 50 ms) | V |
| 33 | `u_min_steering` | min. battery voltage steering motor controller (last 50 ms) | V |
| 34 | `podstate_counter` | sequence number of the KCU state message | - |
| 35 | `wind_dir` | wind direction at GS, 0 at north, clockwise positive | deg |
| 36 | `wind_vel` | wind speed at ground station | m/s |
| 37 | `gnd_lat` | GS latitude | deg |
| 38 | `gnd_long` | GS longitude | deg |
| 39 | `gnd_alt` | GS altitude | m |
| 40 | `v_reelout` | tether reeling velocity | m/s |
| 41 | `tether_length` | tether length | m |
| 42 | `force` | tether force | N |
| 43 | `u_batt` | GS main battery voltage | V |
| 44 | `est_upwind_direction` | average upwind direction (last 300 s) at 6 m height | rad |
| 45 | `est_wind_velocity` | average wind velocity (last 300 s) at 6 m height | m/s |
| 46 | `est_app_wind_kite` | estimated relative flow velocity at kite | m/s |
| 47 | `pos_east` | position of kite relative to GS | m |
| 48 | `pos_north` | position of kite relative to GS | m |
| 49 | `height` | estimated height of kite above GS | m |
| 50 | `elevation` | elevation angle | rad |
| 51 | `azimuth` | azimuth angle, 0 straight downwind, positive to right | rad |
| 52 | `kite_distance` | radial distance swivel head to furthest point on kite | m |
| 53 | `heading` | heading angle | deg |
| 54 | `course` | course angle | deg |
| 55 | `est_tether_length_reelout`  | length of deployed tether (reference point: swivel) |  m |
| 56 | `rel_steering` | relative steering input | % |
| 57 | `rel_depower` | relative depower input | % |  
| 58 | `set_steering` | set value of the steering | - |
| 59 | `set_depower` | set value of the depower | - |

## Other information

- Launch of the instrumented kite power system recorded by an onboard video camera mounted on the measurement setup [[7]](#Oehler2018c)
- Photo of the instrumented kite power system on the ground, just before launch
- Document describing the calibration of the measurment setup  


## References

<a name="Oehler2018b">[1]</a> Johannes Oehler, Roland Schmehl: "Aerodynamic characterization of a soft kite by in situ flow measurement". Wind Energy Science, 2018. https://doi.org/10.5194/wes-2018-46

<a name="Oehler2017">[2]</a> Johannes Oehler: "Measuring apparent flow vector on a flexible wing kite". MSc Thesis, University of Stutgart, 2017. https://doi.org/10.18419/opus-9890

<a name="Vlugt2013">[3]</a> Rolf van der Vlugt, Johannes Peschel, Roland Schmehl: "Design and Experimental Characterization of a Pumping Kite Power System". In: Uwe Ahrens, Moritz Diehl, Roland Schmehl (eds.) Airborne Wind Energy. Green Energy and Technology, chap. 23, pp. 403–425, Springer, Berlin Heidelberg, 2013. https://doi.org/10.1007/978-3-642-39965-7_23

<a name="JerezVenegas2017">[4]</a> Marcos Jerez Venegas: "Path Optimization of a Pumping Kite System". MSc Thesis, Delft University of Technology, 2017. http://resolver.tudelft.nl/uuid:0a67e3e9-358a-494f-a553-b65ed9f3c8c6

<a name="VanReijen2018a">[5]</a> Marc van Reijen: "The turning of kites: A quantification of known theories". MSc Thesis, Delft University of Technology, 2018. http://resolver.tudelft.nl/uuid:5836c754-68d3-477a-be32-8e1878f85eac

<a name="Oehler2018a">[6]</a> Johannes Oehler, Marc van Reijen and Roland Schmehl: "Experimental investigation of soft kite performance during turning maneuvers". Journal of Physics: Conference Series 1037 052004, 2018. https://doi.org/10.1088/1742-6596/1037/5/052004

<a name="Oehler2018c">[7]</a> Johannes Oehler, Roland Schmehl: "Kite onboard setup for in situ measurement of relative flow". Video footage from onboard camera, 2018.
https://doi.org/10.5446/37575

## Author

Roland Schmehl, Email: r.schmehl@tudelft.nl

## License

This data set is licensed under the [![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/4.0/)

## Acknowledgments

The kite power system was operated by
- Bert Buchholz, Kitepower BV, as Central Control Operator,
- Johannes Peschel, Kitepower BV, as Kite Pilot,
- Pietro Faggiani, Kitepower BV, as Winch Control Operator
- Johannes Oehler, TU Delft, as Measurement Engineer
