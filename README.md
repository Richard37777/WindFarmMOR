%%%%%% 0. DESCRIPTIONS %%%%%%

This is a demo of the data-driven model order reduction method proposed in the paper ''Model Order Reduction of Large-Scale Wind Farms: A Data-Driven Approach''. Provided with a simple benchmark model of the multiple-input-multiple-output (MIMO) systems, the corresponding reduced-order models (ROMs) and bode plots are produced by this illustrative demo.

%%%%%% 1. SYSTEM REQUIREMENTS %%%%%%
- Dependencies: to run the code an installation of MATLAB/Simulink R2023b or later versions is required.

- Version of software for testing: the code has been tested on a Windows 10 Pro machine and MATLAB/Simulink R2023b.

- Non-standard hardware: no non-standard hardware is required.


%%%%%% 2. INSTALLATION GUIDE %%%%%%
- Instructions: no installation is required.

- Typical install time: N/A.

%%%%%% 3. DEMO %%%%%%
- Instructions to run the demo: open in MATLAB one of the files with the name formatted as "run_MOR.m" and either a) press F5 on the keyboard or b) click on "Run" in the EDITOR tab. Alternatively, type the name of the file to run in the MATLAB command window without the ".m" extension and press enter.

- Expected input: the linearised full-order model(FOM) to be reduced. A simple benchmark model of multiple-input-multiple-output(MIMO) systems is imported as default in this illustrative demo. For more benchmark models, see https://www.slicot.org/20-site/126-benchmark-examples-for-model-reduction. Users could use their own models according to their preferences.  

- Expected output: MATLAB figures and the reduced-order models(ROMs). The ROMs are saved as "ROM.mat"(Model-based) and "ROM_DD.mat"(Data-driven) in the folder.

- Expected run time: around five minutes, normally no more than ten minutes. This takes time because the Full Order Model(FOM) is simulated to collect the data. If the data is already collected (e.g. from the real system), then the running time could be significantly reduced by loading the collected data.

%%%%%% 4. INSTRUCTIONS FOR USE %%%%%%
- Software description: the software is organised in several MATLAB m files and Simulink slx files. As far as the MATLAB files are concerned, one of them is the script producing the figures and ROMs, and the rest are MATLAB functions used within the script. The two Simulink slx files represent the direct and swapped interconnection as Fig 1 and Fig 2 in the manuscript. A brief description of the files is as follows.
	+ run_MOR.m: scripts to run to obtain the MATLAB figures and the ROMs.
        + FOM.mat: the linearised FOM to be reduced. Can be changed with user's own models.	
        + Algorithm_1.m: Algorithm 1 as introduced in the Section 3 of the manuscript.
        + Algorithm_2.m: Algorithm 2 as introduced in the Section 3 of the manuscript.
        + drawbodeplot.m: MATLAB function to draw the bode plots.
        + Interpolation.m: construct the associated S and Q matrices for the selected interpolation points as introduced in the Section 2A and 2B in the manuscript. 
        + Interconnection_Directed.slx: the model of direct interconnection as Fig 1 in the manuscript. run automatically in the "run_MOR.m" to collect the data for Algorithm 1. 
        + Interconnection_Directed.slxc: Simulink cache for speeding up the simulation of "Interconnection_Directed.slx".      
        + Interconnection_Swapped.slx: the model of swapped interconnection as Fig 2 in the manuscript. run automatically in the "run_MOR.m" to collect the data for Algorithm 2. 
        + Interconnection_Swapped.slxc: Simulink cache for speeding up the simulation of "Interconnection_Swapped.slx".    
        + "slprj" folder: contains necessary files to run the slx files. 
- How to run the code on the data: the MATLAB script "run_MOR.m" can be run as described at point 3. They internally run the previously mentioned MATLAB functions, which in turn process the data collected from the slx files to produce the ROMs.

- Production instructions: by running the MATLAB script "run_MOR.m", the bode plots of the direct interconnection, swapped interconnection and the ROMs are obtained as an output. The ROMs are saved as "ROM.mat"(Model-based) and "ROM_DD.mat"(Data-driven) in the same folder.


	
