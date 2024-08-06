# GENERALIZED GROUND MOTION MODEL (GGMM) (SUBDUCTION)


This tool, named as Generalized Ground Motion Model for Subduction environment (GGMMSubd), uses a hybrid Recurrent Neural Network (RNN) framework to estimate a 35×1 cross -dependent vector (denoted as IM) of RotD50 Spectral Acceleration (RotD50S_a) at 31 periods and geometric means of Arias Intensity (I_(a,geom)), Significant Duration (D_(5-95,geom)), Peak Ground Acceleration (PGA_geom) and Peak Ground Velocity (PGV_geom) using a set of seismic source and site parameters as inputs. The source and site inputs to the RNN framework include a vector of 6 values including Subduction fault slab mechanism (F), magnitude (M_w), closest rupture distance (R_rup), Joyne-Boore distance (R_JB), soil shear-wave velocity (V_s30), and hypocentral depth (Z_hyp). The residuals of the RNN framework are used to construct between-event and within-event covariance matrices to account for the between-event and within-event variabilities of the ground motions. Hence, given the source and site parameters, this tool returns a median prediction of the IM and estimated correlated variance bands. The executable is developed by Jawad Fayaz (https://jfayaz.github.io/layouts/codeandsoft.html/) and collaborators (Miguel Medalla, Pablo Torres, and Carmine Galasso). For further details please read the article mentioned in the “Reference”.

Download the application from the following Dropbox link

    https://www.dropbox.com/scl/fo/lqcz9p7sk2mea3a1itlx5/AD6Z9OJWoQMyk5Y-svSxKH0?rlkey=l0wh0v5le3nu05mz8rtrjqu87&dl=0


1. 	GGMMSubd Inputs (in order)
	
    Subduction Fault Mechanism (F)

          Subduction Mechanism (F)	Value

          Interslab	0

          Intraslab	1

    Magnitude (Mw): 3≤M_w≤9
	
    Closest Rupture Distance (Rrup) in kilometers (km): 0≤R_rup≤300
	
    Depth of Hypocenter (Zhyp) in kilometers (km): 0≤Z_hyp
	
    Joyne-Boore Distance (RJB) in kilometers (km): 0≤R_JB≤300
	
    Shear-Wave Velocity (Vs30) in meters per second (m/s): 0≤V_s30≤3000
	
    Conditional Period (T*) 

        IM	Input for T*
      
        PGV_geom	-3
	
		D_(5-95,geom)	-2
	 
		I_(a,geom)	-1

        PGA_geom	0

        T=0.01	0.01

        T=0.05	0.05

        T=0.1	0.1

        T=0.15	0.15

        T=0.2	0.2

        T=0.25	0.25

        T=0.3	0.3

        T=0.4	0.4

        T=0.5	0.5

        T=0.6	0.6

        T=0.7	0.7

        T=0.8	0.8

        T=0.9	0.9

        T=1.0	1.0

        T=1.2	1.2

        T=1.4	1.4

        T=1.6	1.6

        T=1.8	1.8

        T=2.0	2.0

        T=2.25	2.25

        T=2.5	2.5

        T=2.75	2.75

        T=3.0	3.0

        T=3.25	3.25

        T=3.5	3.5

        T=3.75	3.75

        T=4.0	4.0

        T=4.25	4.25

        T=4.5	4.5

        T=4.75	4.75

        T=5.0	5.0


    Name of Output Folder (OutputFolderName)
  
  
  
2.	Calling GGMMSubd 

    The tool package consists of the executable application “GGMMSubd.exe” which can be easily called from any command line or programming language/software. An example to run the GGMM program is given in Figure 1 (check Manual) where the inputs are in the same order as mentioned in above section “GGMM Inputs”. The generalized syntax to run the executable is as follows:
    
        GGMMSubd.exe   F   Mw   Rrup   Zhyp   RJB   Vs30   T* OutputFolderName
    In case all the inputs are not properly provided the tool will throw an error as shown in Figure 2 (check Manual).
 
 
3. 	GGMMSubd Outputs

    The tool creates a folder named as inputted by the user in the OutputFolderName (as described) within the current directory of the tool. The output screen of the framework is shown in Figure 3 (check Manual).

    The outputs consist of two files: 1) “GGMM.out” file containing the estimated median IM predictions and its conditional correlated variance bands (hence there is no variability at T*) and 2) “GGMM.jpg” file showing the median and sigma bands of the estimated intensity measures in IM vector. The outputs are shown in Figures 4 and 5 (check Manual). 
 


   Reference
        
	Jawad Fayaz, Miguel Medalla, Pablo Torres, and Carmine Galasso (2023). "Recurrent Neural Networks based Generalized Ground Motion Model for Chilean Subduction Seismic Environment". Structural Safety. https://www.sciencedirect.com/science/article/pii/S0167473022000893?via%3Dihub.

