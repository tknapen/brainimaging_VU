# Preprocessing 

## Why preprocessing?

Why can't we just start the interesting analses we thought we would do as our data come out of the scanner? Well, functional images need to be aligned with the anatomy, and because they are warped, they also need to be *unwarped*. Moreover, we need to perform motion correction so that a voxel remains in the same location relative to the anatomy independent of subject motion: many of these steps center on knowing exactly what happened where in the brain. Needless to say, in all these are a lot of different steps and programming all of them would be a herculean effort for any one person. On top of this, it's actually necessary to inspect the results of all the preprocessing steps to make sure that the automated processing steps don't go awry. 

## Why quality control?

fMRI and MRI can go wrong in many different ways. A coil contact can get loose, breaking the electrical connection - causing strange artifacts. Something made of metal (think, subjects with braces) can start to function like an antenna or just distort the magnetic field and thereby interfere with the MRI acquisition. Or your subject could have moved too much. How do we check for all of these? Like the preprocessing, setting up and performing all these checks would be an enormous amount of work. 

## MRIQC & fmriprep

Luckily, the Poldrack lab at Stanford have developed a couple of pipelines that make both these tasks a lot easier. Both of these tools take a BIDS formatted dataset and run it through an entire automated pipeline of processing steps in a containerized environment (which doesn't depend on the computer that runs it - it's always exactly the same). 

This practical will focus on interpreting the outputs of these tools, since they give a good idea of how things can go 'kaput'. First setp: go ahead and read the startpages of the two packages [here](https://fmriprep.org/en/stable/) and [here](https://mriqc.readthedocs.io/en/stable/). If you end up having to run them yourself as a part of your internship, you'll know where to go for further information. But for now, go through the posters that are featured on these front pages to give yourself an idea of what these packages do. 

*Supporting info - * As an example of the ideas behind these reports, read [the 'carpetplot' paper](https://doi.org/10.1016/j.neuroimage.2016.08.009).

# MRIQC

Step 1: go to [http://aeneas.labs.vu.nl/mriqc/reports/bold_group.html](http://aeneas.labs.vu.nl/mriqc/reports/bold_group.html) to find the output of MRIQC for an experiment we ran two years ago: 40 subjects performed a reinforcement learning experiment in the 7T across multiple sessions. 
We'll be looking at the functional MRIQC outputs, and focus on several image and signal quality measures. The group bold report shows all of the fMRI runs (over 200 of them in the entire experiment) as scatter plots for each of the quality measures, or image quality metrics (IQMs) in mriqc parlance. To find out what they are, you can consult the [mriqc explanation](https://mriqc.readthedocs.io/en/stable/iqms/bold.html). In the our report, you can click each of the points to go to a follow-up page for that specific run. Let's go through a bunch of IQMs and see how the scanner and our subjects performed! 

*For each of these IQMs, pick a 'good' run and a 'bad' run, and try to figure out what the difference between these runs is. This could be in the scanner performing weirdly, or a difference in the participants' behavior. Note these down for yourself!*

1. SNR - this is a measure of image quality that can also be calculated for anatomical images - here applied to functional images. 
2. DVARS - the single column figure gives a summary measure. DVARS indexes the rate of change of BOLD signal across the entire brain at each frame of data, and thus can be used as a crude indicator of data quality. Motion and spike artifacts (a single TR gone completely awry) will increase DVARS values. 
3. FD (mm) - this is a summary measure of the motion a subject went through. Check out the FD (mm) timecourse in the report - and check out the effects on the carpet plot below!
4. tSNR - a measure used by MR physicists to assess stability of the scans. If the scan has a lot of noise, this measure will be lower. From the equation on the MRIQC website, why do you think that is? What sets the good and bad runs apart? Is it just the subject or the scanner that is misbehaving, or both?

#### Extra questions:

Pick the run-report of a few runs of the type `ses-2_task-RLtestphase`. This experiment often finished before the scan itself, so that the acquisition would continue longer than the experiment, and subjects were looking at the desktop of the computer that ran the experiment. Can you find evidence of this happening in the carpetplot and associated time courses? What happened? What effect would including this stretch of data in the tSNR calculations have?

This experiment was run using a multiband sequence. What this means is that 3 slice packages were simultaneously acquired, speeding up scanning tremendously. But perhaps there were also downsides? Can you see evidence of this in the MRIQC outputs?


# fmriprep

Step 1: go to [http://aeneas.labs.vu.nl/fmriprep/prf_lyon/sub-01.html](http://aeneas.labs.vu.nl/fmriprep/prf_lyon/sub-01.html) for an example fmriprep output. fmriprep is similar to MRIQC, but is more elaborate. It also does full anatomical and functional preprocessing, and its outputs can be in volumetric and surface formats (projected onto the gray matter ribbon). The outputs it generates are sometimes similar to those of MRIQC, but tend to be more complete. For anatomical images, it segments different tissue types, aligns the anatomy to a volumetric template - the MNI space, and performs full white matter - gray matter and pial surface reconstructions using a package called FreeSurfer (for those surface formats). 

One nice thing about fmriprep outputs is that the images are dynamic. Try to hover over the first **"Susceptibility distortion correction"** figure of a functional run. You will be able to see the effects of the distortion correction (unwarping) because it shows you a before and after image of this makeover - with the white matter outline for reference!

fmriprep also tries to characterize the noise in your scans by looking at the signals in white matter and CSF. Because we don't expect any relevant signals in these tissue types, they feature only noise. This noise can also be present in the gray matter, so it could give us a way of de-noising the gray matter signals we're interested in. More on that later. 

fmriprep also co-registers the unwarped EPI functional image to the surfaces of the anatomy. In the section **"EPI to T1 registration"** you can find examples of this. Looks great, right? But wait, one run went wrong! Which is it?

fmriprep also characterized signals in a carpet plot. The subject in this experiment, was he/she better or worse than the subjects in the MRIQC outputs? How can you tell from the carpetplot?

