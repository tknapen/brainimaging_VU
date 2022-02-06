# Brainimaging VU

This is the repository for the brainimaging course for AI and psychology master's students at the Vrije Universiteit Amsterdam (**P_MBRIMAG** & **P_MBRIMAG_AI**). In this 8-week course, we teach you the basics of fMRI imaging, from data acquisition and formats to analyses and inference. At the end of the course, you will be able to devise a valid fMRI experiment, and perform the basic analysis on the resulting data. That is, we will teach you everything from the basics of signal analysis, to experimental design, to statistics. The course is short, so our goal is to give you an idea of the awesome possibilities and annoying pitfalls of functional brain imaging. But most importantly, to teach you how Open Science fMRI research works, and give you a solid foundation for further learning. 

You can find the schedule for the course on [rooster.vu.nl](http://rooster.vu.nl).

Your grade will depend on an exam (60%) and a final report (40%). Note that these percentages and the course content have been upgraded to be lockdown-proof, so they will perhpas be different from the original course summary on vunet. The exam materials are the first part of the award-winning lecture series by Lunquist & Wager on [YouTube](https://youtube.com/playlist?list=PLfXA4opIOVrGHncHRxI3Qa5GeCSudwmxM), as well as the literature discussed in the lectures and practicals. To practice fMRI analysis, you will work through explanatory Jupyter notebooks for the practicals. During the final half of the course, you will analyze an fMRI dataset yourself and write a report on it in the Jupyter notebook format. 

### What is the course material exactly, and what isn't?

What do I expect you to know by the end of the course? An example exam from a previous year (2019's re-exam) has been uploaded to canvas (you can find it under "exam preparation"). Beware: since the course content has changed, some of the questions have been crossed out: they aren't part of the exam materials for this year. There will also be open questions in this year's exam; these will be about the projects you're doing and are bonus materials.

**Everything discussed in my own lectures and in the YouTube lectures listed in the materials table below is exam material, as well as everything in the practicals, with the following caveats: I will not ask you to reproduce equations, will not quiz you on linear algebra, and I will not ask detailed statistical questions.**

What is important for the exam? Of course, my own lectures and the practicals give you the most important information as these are pre-screened by yours truly. Anything that is mentioned both in my lectures and in the YouTube lectures, or in the practicals and in the YouTube lectures, is important! Sometimes the YouTube lectures, the teachers use jargon. If I don't explain these terms in my lectures or the practicals, these terms (things like 'spin history', 'restricted maximum likelihood methods', etc) are not part of the exam materials. 

## Contact & Office hours

I can be contacted through email [tknapen_teaching@gmail.com](mailto:tknapen_teaching@gmail.com), but be sure to put ***[Brain Imaging]*** in the subject line to trigger my response as soon as possible. As I work both at the VU and [Spinoza Centre (KNAW)](http://www.spinozacentre.nl) I divide my time between the two. But I will do my best to schedule a face to face Zoom meeting as soon as you need guidance.

### Teaching Assistants

Jet Lageman & Ron van de Klundert, both PhD students in the lab, will support you in the practicals. They will be on call during the hours at which the practicals are scheduled, and will monitor the questions (discussions) section on Canvas. 

## Lectures

How do you go about this course as a student? With the possibility of a lack of direct face to face interaction due to Corona, we've Corona-proofed the course such that your learning of the basic materials is more self-paced. It's important to try to watch the YouTube modules before the lectures, since our own lectures improve and extend the materials of the YouTube modules. Don't worry - if you haven't been able to do this our own lectures will be recorded so you can cross-reference these. So, you can work on these in your own time, which we hope will make your participation more corona-proof. 

The Zoom links for the lectures can be found on Canvas, in the Zoom menu. Lectures will be recorded and uploaded after conversion and edits - we aim to upload on the day of the lecture.

***Friday Lectures*** The class interactions on Fridays, especially later on in the course, are intended to be based more on *interactive discussion* than regular sit-and-listen lectures. These discussions will be based on both *advanced topics* and Perusall reading materials. 

## Practicals (& Discussions)

Think of these as a question hour for both the theory and the practicals. The practicals will not be graded, but serve to give you a backbone for the things that you'll also have to do for the final project. That is, they teach you the different things that you'll need to know to be able to perform the project. 

The practicals will be given in the format of Jupyter notebooks, which you can run on [google colaboratory](https://colab.research.google.com/). Those of you that have already completed Neural Models will be familiar with the format. Note that you will need a Google account for accessing collaboratory notebooks. You can navigate and open the notebooks in Colab by clicking the 'open in Colab' buttons below. Make sure to copy them to your own Google Drive. If you want to know more about Colab, see the ["Welcome to Colab" Website](https://colab.research.google.com)

The first practical is not necessarily a practical, but is a Python refresher taken from the Neural Models course: 
"Practice" Python Practical [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tknapen/NMCP_AI_2020/blob/main/practicals/python_tutorial.ipynb)

### Actual Practicals

***Practical 1:*** *GLM Practical* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tknapen//brainimaging_VU/blob/main/notebooks/glm.ipynb)

***Practical 2:*** *Preprocessing Practical* 
This tutorial is all about interpreting the outputs of preprocessing steps, so this tutorial will guide you through [preprocessing](notebooks/preprocessing.md).

***Practical 3:*** *Nuisance Regression* 
This tutorial is all about how we use the preprocessing information to clean our data [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tknapen//brainimaging_VU/blob/main/notebooks/nuisances.ipynb).

***Practical 4:*** *K-space tutorial* 
This tutorial explains where our images come from, and aims to give you some understanding of the basics of MRI image generation (will be uploaded before week 4) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tknapen//brainimaging_VU/blob/main/notebooks/kspace.ipynb).

The general goal of these practicals is to teach you the best & most modern open science practices, as well as show you the strength of the python-based open source ecosystem. Our goal is to show you the way forward, if you are going to use fMRI or imaging yourself in your future research career. 

## Perusall

We will read some literature, mostly recent reviews on current topics in fMRI, on Perusall. You can get to the Perusall course website from the Canvas menu. Assignments of reading material will start after the first couple of weeks. 

## Project

To give you a taste of the practice of fMRI research, we're preparing multiple project outlines, in which you team up with 1 or 2 of your fellow students to analyse an fMRI dataset together. We hope this team-effort will provide a lockdown surrogate for actual interaction. 

The different projects each focus on a specific type of analysis and experiment, and you will be able to submit your preference for the exact project. You will jointly produce a single Jupyter notebook report, in which you write an introduction about the experiment and the dataset, perform (a set of different types of) analysis, and interpret the results. We will provide you with a couple of literature references as underlying theory, but you will have to search for your own literature to supplement the provided information. 

Grading: After the deadline, you will receive 3 project reports to grade based on a predefined rubric, which we will upload on Canvas. Of course, we will also grade the reports ourselves - using the same rubric. Please also consult this Rubric if you're wondering what is important to get right. 

The notebook that you need to start work on for the project is in this repository:
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tknapen//brainimaging_VU/blob/main/notebooks/backbone_projects.ipynb).

## Exam

As things stand now, the Exam will be held in the VU standard proctored TestVision environment, proctorIO. It will consist of a mix of multiple choice and open-ended questions. 

## Timeline of the Course

We are working on the detailed timeline, this will be updated asap. 


