# RespirationET
This data includes the code used to process the respiration data extracted from videos of infants in front of the eye-tracker and its relation to the extracted eye-tracker data and movement extracted data.

This project has been developed by:
- David López Pérez -> d.lopez@psych.pan.pl. -> coordinator of this project and Matlab coder
- Anna Bożuk -> a.bozuk@student.uw.edu.pl -> extraction of the respiration data and python processing
- Agnieszka Wojtowicz -> am.wojtowicz@student.uw.edu.pl -> extraction of the respiration data and python processing
- Agata Kozioł - > aa.koziol2@student.uw.edu.pl -> extraction of the movement in front of the eye-tacker
- Zuzanna Laudańska -> zlaudanska@psych.pan.pl -> ET data acquisition 
- Przemysław Tomalski -> ptomalski@psych.pan.pl -> Head of the Babylab UW & PAN where the data was acquired

# Extracted data for this study:
  - Computer vision algorithm to extract movement in front of the eye-tracker
  - Automatic Respiration quantification from videos
  - Eye-tracker data extracted with a Tobii 60Hz.
  
#  Extracting movement in front of the eye-tracker:
 - Movement Data was extracted using DeepLabCut (Mathis et al., 2018). In total 13 body parts were extracted:
   - Front
   - RightEye
   - LeftEye
   - LeftEar
   - Nose
   - Mouth
   - RightHand
   - RightElbow
   - RightShoulder
   - LeftHand
   - LeftElbow
   - LeftShoulder
   - Trunk
All the files included in this study are attached in the movement folder

# Extracting respiration from videos:
  - Respiration from videos was extracted using a modified version of a matlab script (van der Kooij & Naber (2017)). The method is based on remote photoplethysmography (rPPG) and returns the three best components that describe the changes in a particular area of interest. In this case the main components are assume to be respiration related since movement was quantified in the chest/stomach area.
  - Included here in the respiration extraction folder are the files extracted for each of the three components, together with the files providing the maximum power for the frequency spectrum of each component. 
  - Matlab scripts are included in the Matlab folder:
    + rPPGMod.m is the modified version of the rPPG.m in (van der Kooij & Naber (2017)). The main changes involves 
    + mainrPPG.m -> main script that calls the rPPG function to export the data and save the extracted ICA components data
  
# Eye-tracking data
  - The Eye tracking data was extracted using a Tobii 60Hz. Data includes eye-tracking data in xy coordinates and pupil data that will also be processed together the movement and respiration data.
  
# Data Processing
  - All the processing of the data has been performed in python 3. The python folder contains:
    + cut_to_trials2.py -> reduce the respiration data to the same length as the trial
    + delete_beginning.py > data to remove unnecessary data from the movement and respiration time series
    + get_freq_list.py -> 
    + denoise.py -> function to wavelet denoise the component time series
    + combine_fragments.py -> snipplet to combine the time series of the different files created from a particular video. In same cases the video needed to be splitted in different short videos due to infants movement. Those files are later combined  into a unique respiration file.
    + avi_to_mp4.py -> converter from avi to mp4 to process videos in Matlab
    + split.py -> split the videos into smaller shorter videos
  
  
 # Additional processing files
 - In the excel folder are the additional files needed for data processing.
