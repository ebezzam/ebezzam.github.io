---
layout: page
title: Projects
permalink: /projects/
---

### Finite rate of innovation applied to medical ultrasound imaging (ongoing)

For my master's thesis, I am investigating the use of the _finite rate of innovation_ framework for medical ultrasound imaging, in particular with _plane wave imaging_ to reduce the necessary amount of data needed to reconstruct a meaningful ultrasound image.


### Open source platform for microphone arrays (ongoing)

This has been an ongoing project as part of my Research Scholar' work at LCAV (EPFL) in collaboration with multiple people, in particular my supervisor <a href="http://www.robinscheibler.org/" target="_blank">Dr. Robin Scheibler</a>. The project encompasses algorithms, software, embedded systems, and hardware.

My main contributions:
* development for the <a href="https://github.com/LCAV/pyroomacoustics" target="_blank">`pyroomacoustics`</a> package, most notably the direction-of-arrival (DOA) techniques.
* co-supervised multiple semester projects:

   1. <a href="https://github.com/LCAV/easy-dsp" target="_blank">EasyDSP</a> : a browser-based editor for programming digital signal processing (DSP) in Python on the BeagleBone Black (BBB).

   2.<a href="https://github.com/Scrashdown/PRU-Audio-Processing" target="_blank">PRU Audio Processing</a> : using unique microcontrollers from the BBB to perform the front-end audio processing (downsampling and low-pass filtering) for an array of PDM microphones. Moreover, a C API was built to conveniently access audio samples in real-time for processing.

   3.machine learning pre-processing additions to `pyroomacoustics` (ongoing)
* designed, 3D-printed, and assembled a lamp that can be programmed in Python to display awesome colors using data collected from the microphone array.

This project has been involved with three papers during my time at LCAV:
* <a href="http://ieeexplore.ieee.org/document/8005297/" target="_blank">ICASSP 2018 Demo</a>
* <a href="https://arxiv.org/abs/1710.04196" target="_blank">`pyroomacoustics` paper</a>
* <a href="http://ieeexplore.ieee.org/document/7952744/" target="_blank">FRIDA algorithm for DOA</a>

### A cognitive robot for helping identify motor disabilities (HackZurich 2017, 2nd place out of ~150 projects)

We used ABB's YuMi robot, Microsoft's Cognitive Services, and OpenCV to automate a concise version of the <a href="http://www.pearsonclinical.co.uk/Psychology/ChildCognitionNeuropsychologyandLanguage/ChildPerceptionandVisuomotorAbilities/MABC-2/MovementAssessmentBatteryforChildren-SecondEdition(MovementABC-2).aspx" target="_blank">Movement Assessment Battery for Children</a> test to help identify motor impairment. You can read more about the project on <a href="https://devpost.com/software/jred" target="_blank">DevPost</a>.


### Beamformer design tool (internship at DSP Concepts)

During a six-month internship at DSP Concepts, I developed a _Beamformer Design Tool_ in order to meet the growing need of microphone array processing with the advent of smart speakers such as Amazon Alexa and Google Home. The core of the tool was to design fixed beamforming weights in the frequency domain given a certain set of parameters such as the microphone array, the microphone directivities, and a desired source direction. Moreover, four different algorithms could be used to design the beamformer(s) which could take into account a desired minimum beamwidth, the expected signal level, the expected diffuse noise level, etc in order to optimize the signal-to-noise ratio (SNR). Different beamformers could be compared and evaluated interactively over a variety of criteria such as SNR gain, polar patterns, beamwidth, and uncorrelated noise gain over all frequencies. Finally, the tool was linked with DSP Concept's proprietary tool - AudioWeaver - in order to conveniently export the designed weights and even design the beamformer(s) within AudioWeaver.

I also used the tool to design (2-, 4-, 7-) microphone arrays that would perform well with our beamforming and direction-of-arrival (DOA) strategies.

An additional component of the intership was to validate the performance of the beamformer designs by measuring the SNR gains and polar patterns in a sound-isolated remove and using wake-work recognition improvement as a "proxy" for automatic speech recognition (ASR) improvement. 

A white paper which describes some of the beamforming and DOA strategies can be found <a href="https://dspconcepts.com/sites/default/files/voice_ui_part2.pdf">here</a> and another on voice user interfaces <a href="https://dspconcepts.com/sites/default/files/fundamentals_of_voice_ui.pdf">here</a>.


### A Python implementation of DeepFool (semester project at LTS4)

During this semester project, I implemented the <a href="https://arxiv.org/abs/1511.04599">DeepFool</a> algorithm in Python and developed a "blackbox" approach, i.e.\ a situation in which we do not have full access to the classifier structure as is normally required by DeepFool. As well as applying this blackbox approach to ``academic'' networks, such as those submitted for the <a href="https://arxiv.org/abs/1511.04599">ILSVRC</a> competition, I also applied it to a commercial classifier - Clarifai - to gauge the robustness of products in the area of image classification and object recognition. An implementation of DeepFool for Google's Cloud Vision, IBM's Visual Recognition, Amazon Rekognition, and Microsoft's Computer Vision APIs was also made but not extensively tested but to limited query credits.

Coming soon: report download


### DoctorBot : a chatbot for medical advice (HackZurich 2016, top 25 out of ~150 projects)

We built a chatbot within Facebook that integrated several APIs to provide medical advice and suggest a nearby doctor. You can read more about the project on <a href="https://github.com/ebezzam/DoctorBot">GitHub</a>.


### Compressive sensing based beamforming demo for medical ultrasound (semester project at LTS5)

I developed a MATLAB GUI and software for a demo of plane-wave medical ultrasound imaging based on compressive sensing techniques. This would interface with the FPGA-based ultrasound device on <a href="http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7468550">ULA-OP</a>. I was part of the team presenting the algorithm/platform at the <a href="http://www.nano-tera.ch/pdf/posters2016/UltrasoundToGo250.pdf">2016 Nano-Tera Meeting</a> poster session.

Coming soon: report download


### GSM Codec Identification (Fraunhofer IDMT)

As part of a three-month internship during my Bachelor's, I worked at Fraunhofer IDMT in Ilmenau, Germany. There, I investigated and prototyped algorithms in Octave for GSM codec identification and for a few codecs tampering detection. For my thesis, I ported the implemntation to C++ so that it could be integrated with the IDMT's other codec identification techniques. Finally, I used IDMT's annotation and testing framework to evaluate the performance of my algorithms.

