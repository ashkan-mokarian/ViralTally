# ViralTally
Tracking the number of infected cells normalized by number of Plaques in microscopy timelapse videos of infection and plaque datasets.

# Creating the Dataset

## Consolidate Dataset
Use the notebook `notebooks/01_consolidate_files.ipynb` to create folders for each experiment type and sample.

## Preprocess images
In order to obtain better results, in Fiji run the following batch process to remove the background, in particualr
for the GFP channel by going in Fiji to `Process->Batch` and running the following script:
`run("Subtract Background...", "rolling=50 stack");`

## Create tracking and spots csv file
Again in Fiji, by using `Plugins/Trackmate` go through the best parameter setup that gives you the results needed and
save the tracking results as a .xml file. You can find such a file in `dataset/Sars2Plaque/trackmate/A01_s1.xml`.
Then by `plugins/tracking/trackmate_batcher` create the spots .csv files.
