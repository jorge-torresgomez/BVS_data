# BVS_data
In this repository, it is accessible the data provided by the [BloodVoyagerS framework](https://github.com/RegineWendt/blood-voyager-s) and the code to process this data to provide different representations.

The data file `1000Bots_500s_3accuracy.csv` provides a table with 7 columns according to the coordinates of flowing nanosensors in the Human Circulatory System: 
1. Column 1 provides the [vessel ID](https://github.com/RegineWendt/blood-voyager-s/blob/master/Images/table1.pdf)
2. Column 2 to 4 the [3D coordinates](https://github.com/RegineWendt/blood-voyager-s/blob/master/Images/table1.pdf)
3. Column 5 provides the time variable.
4. Column 6 is the vessel ID.
5. Column 7 is the vessel stream.

The code file `code_file.mlx` written in [MatLab](https://www.mathworks.com/products/matlab.html) processes this data is written identifying the main parameters per closed circuit in the vessels. The closed circuits are always assumed to start and end at the Left Heart and follow the path per tissue represented in the BloodVoyageS framework, i.e., the Head, the Shoulders, the Thorax, etc.
The code provides the following outputs also supported graphically supported by plots:
In the Spatial Domain:
1. The path (according to the vessel segment) followed by each nanosensor.
2. The nanosensors traveling per closed-circuit starting and ending at the Left Heart.
In the Time Domain:
3. The time instants when the nanosensor goes through the Left Heart.
4. The periodicity in seconds for the traveling path.
Concentration level of particles:
5. The concentration level that a particle senses. That is the total of neighbors nanosensors on each vessel segment where the current nanosensor is traveling through.
6. The concentration level per closed circuit.
7. The cumulative and average concentration level that a particle senses after a round trip. i.e., starting and ending at the Left Heart.
