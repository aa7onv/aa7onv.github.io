---
layout: page
title: Three-Band Audio Equalizer
description: Audio Engineering
img: assets/img/3band.png
importance: 2
category: work
giscus_comments: false
---

# 3 Stage Active tone Control

--- 

### Circuit Design/Verification using LTSpice
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3band.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Stage 1: Inverting Buffer circuit
This buffer amplifier provides a buffered output of the input signal to be filtered or equalized by the three-band filters. The capacitors block the DC signal and only allows the AC signal from the audio input to pass, helping to isolate the input

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/stage1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Stage 2: Inverting Buffer circuit
The next stage is a voltage offset circuit. The TL072 op amp is unable to amplify the negative peaks of the input signal  since we are using a single 12V positive rail. 
So we need to offset the voltage 6V. The offset is made up of a voltage divider, along with 3 capacitors that act as filter before the signal gets sent to the positive feedback of the opamp.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/stage2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Stage 3: Tone Control
This is where the tone filtering happens and it consists of the 3 pass filters connected in a negative feedback loop with the TL072 opamp. After the signal passes through the C3 capacitor, the signal goes through the three-band filters which are each made up of RC filters. The potentiometers are used as a variable resistor to affect the cutoff frequencies of each band of the audio signal.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/stage3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Built ciruit
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/circuit.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Cutoff  Frequency  Calculations
To determine the cutoff frequency, we use the below formula
<br>
$$
f_c = \frac{1}{2\pi CR}
$$
<br>
Since the Capacitor value is fixed, we can use the  potentiometer values to  change the frequency response

Heres the math summarized

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/fc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Spectral Analysis
soon

## Results
- About 60-18k Hz range instead of the 20-20k that was intended
- Speaker output was very low, probably due to the cheap quality
- Didn’t quite reach the intended increase / decrease rate of +/- 6dB for each tone as intended


### Sorry, more info will be added soon