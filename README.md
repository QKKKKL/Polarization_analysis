# Polarization Analysis Download KDE Data
This code is adapted from original authos Géraldine Zenhäusern (gzenhaeusern)'s Polarisation Analysis. https://github.com/gzenhaeusern/polarisation-package/tree/main/polarisation_package 

The code are reorganized into Jupyter notebook format.

To call polarisation function, which is where you can actually run the analysis, use:
polarisation(event_name, 0, 0, 1, ptime, stime, args.arg_event_name)

The three numbers each corresponds to plot function, calculate_baz_only function, and save_kde_data_only function. Please always make the first number 0, since this modified code does not work for plotting the original plot designed by gzenhaeusern. If you only want to save kde data, use the line provided above (where first and second numbers set to 0, third set to 1). If you would like to use the calculate_baz_only function from original code, set the second number to 1 and third number to 0.

When you are saving kde data, it returns you three csv files for each event, each for P, S, and Noise. Within each csv file, there will be 6 columns, each corresponding to amplitude value, amplitude frequency, azimuth value, azimuth frequency, inclination value, and inclination frequency. Notice that frequency are the same across each row (there are some redundencies I apologize).

The code expects a input text file with three parts: event name, ptime in seconds, and stime in seconds. The events data are expected to be in RTZ rotation, and filenames ending with '.R', '.T', or '.Z'.

Within polarisation function, event time information are retrieved from input traces. An actually event start time is needed. Timing of noise is set to the period of [start of event, 5 seconds before arrival of P wave]. Please modify according to your actually time frame of noise. The time from start to end of event is the actual event length read from input file, in other words, it is the exact range of data you have. I commented out the wavefrom trimming process within waveform_processing function from original code.

For more information, please refer to the slides attached below.

[KDE_save_and_plot_quick_guide.pdf](https://github.com/user-attachments/files/17639337/KDE_save_and_plot_quick_guide.pdf)


