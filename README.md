# GPC-App
A stand-alone app that allows for the extraction of polymer parameters (Mn, Mw, Mz, PDI, etc) and the tracking of degradation kinetics for large Gel Permeation Chromatography (GPC) data sets 


The goal of this app is to accelerate the analysis of large sets of chromatograms (eg signal vs time plots) extracted from a gel permeation chromatography system, or another kind of size exclusion chromatography system where elution time is a function of molecular weight. 

The app is built using the MatLab appdevloper app, and is packaged to run as a standalone desktop app (it does require the download of the separate matlab runtime, which can be found here: https://www.mathworks.com/products/compiler/matlab-runtime.html). The app is also designed to track the decay in molecular weight in as many as 13 separate groups over an arbitrary amount of time, and fit that data to a first order exponential decay, or a constant rate decay model in terms of either Mn or Mw decay.   


To run the app, data needs to be structured as follows: 
Under an umbrella directory, chromatography data should be stored in a directory labeled TP_n, where n is an integer indicating what timepoint the chromatograms are drawn from. For experiments that use a single endpoint, or are otherwise unrelated to sample degradation, TP_1 should be used. Data should be stored separating time and signal data, where RunTimexx and Signalxx represent the time and signal data from sample xx respectively. TP_n should also contain a text document titled ns.txt, that contains a single column, where each row indicates the number of replicates from each group at that time point. Similarly, a text file sequence_table.txt should be used to label each sample in the time point (including blanks), one label per row. Finally, the upper director that contains the TP_n directories, should include a csv file that contains the reference standard that will be used to interpret the chromatograms. The default settings are for the use of a polystyrene standard in the analysis of a polycaprolactone sample set. 

V.1 There are still some limits in the flexibility of the applet, but I am hopping to make it more adaptable in the future. I have included a sample data set (that was used in a recent manuscript submission). When the paper is accepted or posted on BiorXiv I will add descriptions of the data sets, and code that can be used to plot data extracted from the app. 

The app exports a .mat file that containes all of the parameters calculated in the app, and the specific inputs that led to those outputs. 
