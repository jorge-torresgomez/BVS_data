# BVS_data
In this repository, it is accessible the following

1. Data provided by the [BloodVoyagerS framework](https://github.com/RegineWendt/blood-voyager-s): file `1000Bots_500s_3accuracy.csv`.
2. The code to process the above file accessible in `code_file.mlx`. 
This code, written in [MatLab](https://www.mathworks.com/products/matlab.html), provides main components related to closed path trajectories followed by nanosensors through the Human Circulatory System.
4. The pdf `matlab_arrays.pdf` to graphically support the meaning of the main arrays in `code_file.mlx`.
3. Resulting components stored in the matlab file `BVS_processed_data.mat`.

The data file `1000Bots_500s_3accuracy.csv` provides a table composed of 7 columns according to the coordinates of flowing nanosensors in the Human Circulatory System: 
1. Column 1 provides the [vessel ID](https://github.com/RegineWendt/blood-voyager-s/blob/master/Images/table1.pdf)
2. Column 2 to 4 the [3D coordinates](https://github.com/RegineWendt/blood-voyager-s/blob/master/Images/table1.pdf)
3. Column 5 provides the time variable.
4. Column 6 is the vessel ID.
5. Column 7 is the vessel stream.

The code file `code_file.mlx` processes this data identifying main components per closed circuit in the vessels. 
The closed circuits are always assumed to start and end at the Left Heart. 
The nanosensors follow several circuits according to the variety of tissues represented in the BloodVoyageS framework, i.e., the Head, the Shoulders, the Thorax, etc.
The code provides the following outputs that are also graphically illustrated in plots, the meaning of the main output arrays are given in the pdf document `matlab_arrays.pdf`:

A. In the Spatial Domain:
1. The path (according to the vessel segment) followed by each nanosensor as given by the sequence `path_bot[b_ID,t]`.
2. The nanosensors traveling per closed-circuit starting and ending at the Left Heart in the sequence `path_per_circuit[b_ID,circuit]`.

B. In the Time Domain:

3. The time instants when the nanosensor goes through the Left Heart in the sequence `t_bot_heart[b_ID,t]`.
4. The periodicity in seconds for the traveled circuit the sequence `perd_bot_heart[b_ID,t]`.

C. Concentration level of particles:

5. The concentration level that the nanosensor senses. That is the total of neighbors nanosensors on each vessel segment that simultaneously is also traveling with the given nanosensor. This is given in the sequence `conc_bot[b_ID,t]`.
6. The concentration level per closed-circuit is given in the sequence `conc_curve_circuit[circuit]`.
7. The cumulative and average concentration level that a particle senses after a round trip. i.e., starting and ending at the Left Heart. This is given in the sequences `conc_cumul_circuit[circuit]` and `conc_avg_circuit[circuit]`. 
