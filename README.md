# Predicting Race outcomes in Formula-1













1 Introduction 

In the high-speed, high-stakes world of Formula 1, the difference between victory and defeat often lies in the fractions of a second. This realm of roaring engines and lightning-fast reflexes may seem an unlikely place for data science to make its mark, yet this is exactly where it thrives. Just like a well-oiled engine, the gears of this cutting-edge discipline hum in harmony with the rhythm of F1. From race strategy to car design and driver performance, data science is the invisible co-pilot, charting the path to the podium. In this project, we delve into how data science applications are revolutionizing the world of Formula 1, making it a sleek, digitally driven sport.

1.1 Formula 1

In Formula 1, drivers control high-speed vehicles to be the first to complete a set number of laps, thus securing victory. However, it's not merely about racing; in Formula 1 teams of drivers, mechanics, and engineers work together to integrate technological innovation, strategic planning, and driving skills. Each season, teams participate in a sequence of races, known as Grands Prix, held on various circuits worldwide. These races occur over a weekend, commencing with two practice sessions on Friday, an additional one on Saturday, and a qualifying round. The final race, the true test of endurance and speed, takes place on Sunday.

During Friday's practice session, drivers familiarize themselves with their vehicles to mitigate issues such as understeering or unstable handling. Their performance during Saturday's qualifying rounds is crucial as it determines their starting position for the Grand Prix. A superior performance leads to an advantageous starting position. A lower starting position, on the other hand, imposes a significant challenge, compelling the driver to overtake up to 19 other drivers, each traveling at speeds exceeding 200mph! Qualifying consists of three segments: Q1, Q2, and Q3. In Q1, all 20 drivers have 18 minutes to record their fastest lap. The slowest five are eliminated, securing the final five slots on the grid (starting formation of the cars before the race begins). Q2 follows, lasting 15 minutes, with the five slowest drivers once again eliminated, determining grid positions 11 to 15. Similarly, with Q3 the final round with which the starting order for the Grand Prix is set. Qualifying is a tactical play that influences the race. The top ten qualifiers must commence the race on the tires used to clock their fastest lap in Q2. This rule forces teams to strike a balance between a quicker qualifying time and an optimal race strategy. Meanwhile, those who didn't advance to Q3 have the liberty to choose their tires, occasionally allowing them to deploy innovative strategies to compensate for their grid position deficit. 


The top 10 finishers in each race earn points. The driver securing the first position receives 25 points, the second-place finisher 18 points, the third-place finisher 15 points, and so on, down to the tenth-place driver who is awarded 1 point. Points are accumulated by drivers and teams throughout the season, and the one amassing the most points claims the championship.

Position	Points Awarded
1st 	        25
2nd 	        18
3rd 	        15
4th 	        12
5th 	        10
6th 	         8
7th 	         6
8th 	         4
9th 	         2
10th 	         1



2. Data
In this chapter, we will explore the telemetry data obtained from the FastF1 API, a comprehensive tool for accessing Formula 1 timing and telemetry data. Telemetry data offers intricate details about each lap driven by the Formula 1 cars, providing insights into the performance and strategies adopted by teams and drivers. FastF1 is a Python library that allows users to access Formula 1 timing and telemetry data. It provides functionalities to fetch event schedules, race results, lap times, and detailed telemetry data for each driver.

	Telemetry Data
	Telemetry data in Formula 1 refers to the detailed information collected from various sensors installed on a race car during a race or practice sessions. This data includes metrics like speed, throttle and brake application, gear selection, engine RPM, and tire temperature. It provides real-time insights into the car's performance and the driver's behavior on the track. Teams analyze this data to optimize car setup, improve race strategies, and enhance driver performance, making it an indispensable tool in the highly competitive world of Formula 1 racing. The telemetry data includes several key metrics:
	
	Speed: The car's speed at various points on the track.
	Throttle: The degree of throttle application by the driver.
	Brake: Indicates if and how hard the driver is braking.
	Gear: Current gear in which the car is.
	RPM: Engine revolutions per minute.
	DRS: Status of the Drag Reduction System (DRS)

For our analysis, the focus will be narrowed to key telemetry variables: Speed, Throttle, RPM, and Brake. These specific metrics provide a comprehensive view of a car's performance dynamics and driver behavior. We will aggregate this data across various scales, encompassing individual races and spanning the entire season...... 






To continue reading the full report, please download the 'Honors Project' pdf.


