# Towards robust in vivo quantification of oscillating biomagnetic fields using Rotary Excitation based MRI
M. Gram1,2,*, P. Albertova1,2, V. Schirmer1, M. Blaimer3, M. Gamer4, M.J. Herrmann5, P. Nordbeck2, P.M. Jakob1  
1 Experimental Physics 5, University of Würzburg, Würzburg, Germany  
2 Department of Internal Medicine I, University Hospital Würzburg, Würzburg, Germany  
3 Fraunhofer Institute for Integrated Circuits IIS, Würzburg, Germany  
4 Department of Psychology, University of Würzburg, Würzburg, Germany  
5 Department of Psychiatry, Psychosomatics, and Psychotherapy, Center for Mental Health, University Hospital of Würzburg, Würzburg, Germany  
* corresponding author

# Address for correspondence:
Maximilian Gram, University of Würzburg,
Experimental Physics 5,
Am Hubland, Würzburg,
DE D-97074,
maximilian.gram@uni-wuerzburg.de,
https://orcid.org/0000-0003-2184-3325

# Introduction
This folder contains the original Pulseq based external.seq files used for in vivo REX detection.
The measurements were carried out on the following MRI system:
- Siemens MAGNETOM Skyra, 3.0T
- max. gradient strength = 45mT/m
- max. slew rate = 200T/m/s

# Sequence parameters
## external1.seq
This file contains the spiral readout and can be used for S0 reference imaging. The sequence performs 3 dummy runs and 5 averages with identical readouts. The scans are seperated with Trec=1s from each other. A fat saturation was implemented. The readout uses 4 interleaved spirals with ramped flip angle aquisitions (flip angles: 30°, 35°, 45°, 90°). The FOV is fixed to 240x240mm and the matrix is 96x96. Slice thickness is 5mm and the slice offset is 10mm. The acquisition time is 11ms and n=2000 samples are acquired in each interleave. The rawdata will be 5x4=20 blocks with each 2000 sampling points. The k-space trajectory for image reconstruction was saved in the ktraj.mat file in this folder (units 1/m).
## external2.seq
This file contains one REX detection experiment based on the spiral readout as described above. The sequence uses balanced-spin-locking with tSL=80ms and fSL=50Hz (maximum condition explained in the paper). The tREX stimulus is performed with fstim=50Hz (resonance condition) and Bstim=50nT in the 10mm offcenter slice. The sequence performs 20 repetitions with linear varying relative phases in the range 0...2pi.

## external3.seq
This sequence compares the different spin-lock modules (S-SL, RE-SL, C-SL, B-SL) each in the respective minimum and maximum condition.
S-SL  tSL=77.5ms (max)
S-SL  tSL=80.0ms (neutral, not shown in the paper)
S-SL  tSL=82.5ms (min)
RE-SL tSL=70.0ms (max)
RE-SL tSL=80.0ms (min)
C-SL  tSL=80.0ms (max)
C-SL  tSL=70.0ms (min)
B-SL  tSL=80.0ms (max)
B-SL  tSL=60.0ms (min)
fSL=50Hz, fstim=50Hz, Bstim=50nT @10mm offset, 20 phases

## external4.seq
This sequence runs 14 REX detections (each with 20phases, BSL, tSL=80ms, fSL=50Hz, fstim=50Hz) with different stimulus field strength Bstim = 1, 2.5, 5, 7.5, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100nT.
