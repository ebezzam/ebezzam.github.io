---
layout: page
permalink: /projects/
title: Projects
tags: [projects]
modified: 17-07-2018
comments: false
---

Below are some projects that I have worked on during my studies, at internships, and over weekends at hackathons. Links are provided wherever available!


### Research

* **Microphone array processing (2015-now)**<br>
An ongoing project which was a part of my [Research Scholar](https://ic.epfl.ch/ResearchScholars) experience with [LCAV](https://lcav.epfl.ch/). In collaboration with multiple people, most notably my supervisor <a href="http://www.robinscheibler.org/" target="_blank">Dr. Robin Scheibler</a>, the following tools/data for microphone array processing were developed:
    * Hardware for the [BeagleBone Black](https://beagleboard.org/black): [cape for 8 PDM mics](https://github.com/fakufaku/kurodako), [CompactSix array](https://github.com/LCAV/CompactSix), [Pyramic](https://github.com/LCAV/Pyramic)
    * Software: [browser-based interface](https://github.com/LCAV/easy-dsp), [driver for 8 mic cape](https://github.com/Scrashdown/PRU-Audio-Processing)
    * Algorithms: [pyroomacoustics](https://github.com/LCAV/pyroomacoustics)
    * Data: [Pyramic recordings](https://zenodo.org/record/1209005#.W05WVNgzab8)  
<br />

* [**Sampling at the rate of innovation for ultrasound imaging and localization (Master thesis, 2018)**](https://github.com/ebezzam/frius)<br>
I investigated the application of [_Finite Rate of Innovation_](https://ieeexplore.ieee.org/document/1003065/) (FRI) and [_Euclidean Distance Matrices_](https://arxiv.org/pdf/1502.07541.pdf) (EDM) can be applied to the task of ultrasound imaging and localization.  The target was medical imaging but an application to non-destructive evaluation was also considered.

* [**Python implementation of DeepFool and applying it to commercial classifiers (Fall 2016)**](/pdf/lts4_semester_project_eric_bezzam.pdf)<br>
As a semester project, I implemented the <a href="https://arxiv.org/abs/1511.04599" target="_blank">DeepFool</a> algorithm in Python and developed a "blackbox" approach, i.e. a situation in which we do not have full access to the classifier structure as is normally required by DeepFool. As well as applying this blackbox approach to _academic_ networks, such as those submitted to the <a href="http://www.image-net.org/challenges/LSVRC/" target="_blank">ILSVRC</a> competition, I also applied it to a commercial classifier - <a href="https://www.clarifai.com/" target="_blank">Clarifai</a> - to gauge the robustness of products in the area of image classification and object recognition. An implementation of DeepFool for Google's Cloud Vision, IBM's Visual Recognition, Amazon Rekognition, and Microsoft's Computer Vision APIs was also made but not extensively tested due to limited query credits.

* [**Compressive sensing based ultrasound imaging demo (Spring 2016)**](/pdf/lts5_semester_project_eric_bezzam.pdf)<br>
As a semester project, I developed a MATLAB GUI and software for a demo of plane-wave medical ultrasound imaging based on compressive sensing techniques. This would interface with the FPGA-based ultrasound device <a href="http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7468550" target="_blank">_ULA-OP_</a>. I was part of the team that presented the algorithm/platform at the <a href="http://www.nano-tera.ch/pdf/posters2016/UltrasoundToGo250.pdf" target="_blank">2016 Nano-Tera Meeting</a> poster session.

### Internships

* [**DSP Concepts (Masters internship, 2017)**](https://dspconcepts.com/)<br>
During a six-month internship at DSP Concepts, I investigated various beamforming strategies and developed a **_Beamformer Design Tool_**. With the tool, fixed beamforming weights in the frequency domain could be designed given a certain set of parameters such as the microphone array geometry, the microphone directivities, a desired source direction, a desired minimum beamwidth, and the expected signal and diffuse noise levels.  

    <br>
    Different beamformers could be compared and evaluated interactively over a variety of criteria such as SNR gain, polar patterns, beamwidth, and uncorrelated noise gain. Finally, the tool was linked with DSP Concept's proprietary tool - <a href="https://dspconcepts.com/solutions/audio-weaver" target="_blank">AudioWeaver</a> - in order to conveniently export the designed weights and/or design the beamformer(s) within AudioWeaver. A white paper which describes some of the beamforming and DOA strategies can be found <a href="https://dspconcepts.com/sites/default/files/voice_ui_part2.pdf" target="_blank">here</a> and another on voice user interfaces <a href="https://dspconcepts.com/sites/default/files/fundamentals_of_voice_ui.pdf" target="_blank">here</a>.

* [**Fraunhofer IDMT (Bachelor internship and thesis, 2014 & 2015)**](https://www.idmt.fraunhofer.de/en.html)<br>
As part of a three-month internship during my Bachelors, I worked at Fraunhofer IDMT in Ilmenau, Germany. There, I investigated and prototyped algorithms in Octave for GSM codec identification and (for a couple codecs) tampering detection. For my thesis, I ported the implementation to C++ so that it could be integrated with IDMT's other codec identifiers. Finally, I used IDMT's annotation and testing framework to evaluate the performance of the developed algorithms.


### Hackathons

* [**Speak2Tex (jacobsHack 2018)**](https://devpost.com/software/speak2tex)<br>
Using a [Snips Maker Kit](https://makers.snips.ai/kit/) and the [Console](http://console.snips.ai), we built a voice assistant that can generate the corresponding LaTeX syntax for a wide range of functions and operations: e.g. polynomials, trigonometric functions, integrals, derivatives, matrix operations. We won Bloomberg's Best Tech Prize and GitHub's prize for best Git practices.

* [**A cognitive robot for helping identify motor disabilities in children (HackZurich 2017)**](https://devpost.com/software/jred)<br>
We equipped ABB's [YuMi robot](https://new.abb.com/products/robotics/industrial-robots/yumi) with a "mouth" and "ears" (laptop speaker and microphone + Microsoft Cognitive Services) and "eyes" (Logitech webcam + OpenCV) in order to automate a concise version of the M-ABC Test for diagnosing motor disabilities in children. We were **second place** out of around 150 teams.

* [**Food Cycle: online platform to reduce food waste (Foodhack 2017)**](https://youtu.be/WgaTlFW-41Q)<br>
We developed an online B2B marketplace for food suppliers to connect with entities (such as restaurants and canteens) to sell excess products at a lower price rather than resorting to disposal. We won the _Food Save Challenge_.

* [**DoctorBot: a chatbot for medical advice (HackZurich 2016)**](https://github.com/ebezzam/DoctorBot)<br>
A Facebook chatbot that provides medical advice and can suggest a nearby doctor. Implemented in Python with several APIs (Infermedica, Google Static Maps, API.ai). We were among the **top 25** out of around 150 teams.


<!-- ### Select course projects

* **Embedded Systems**<br>

* **PCML 2**<br>

* **PCML 1**<br> -->



