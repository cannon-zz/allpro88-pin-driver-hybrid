# KiCad Model of Logical Devices' ALLPRO88 Pin Driver Hybrid Module

## Overview

This provides a KiCad [schematic](https://github.com/user-attachments/files/18313998/pin_driver_hybrid.pdf) of the pin driver hybrid modules used in Logic Devices' ALLPRO88 software-driven device programmer.  The service manual scans available on the internet are missing the pages containing the pin driver circuitry.  I have traced out some of my own and guessed at what the SMD parts might be based on their markings and electrical properties.  I believe the schematic is correct, it's certainly correct enough for me to have repaired many of these modules based on what's here, but I found errors as recently as the fall of 2024 so I wouldn't say it's definitely correct.  Your mileage might vary.

The component reference designators are my own invention (there are no markings on the hybrid).  There is a PCB layout, but it's not meant to be used to make actual hybrid modules, it's only meant to help with debugging.  There are no traces or mounting pins.  Only the SMD components are placed in their approximate locations.  The resistors (which in the real hybrids are integrated directly into the traces) are mostly not placed properly at all.  Also, there are several revisions of the hybrid module, I have a mix of several in my own units myself, and the parts placement only matches one of them (I think the oldest version).  Good enough for me.

See also https://github.com/cannon-zz/allpro88-pin-driver.

## Service Suggestsions

Failures I've seen:

 * D1 and D2, the BYM13-30 reverse protection diodes for the TTL high output drivers, fail.  I've seen several do this.  When one of these fails, it becomes resistor-like when reverse biased, and provides a current path to ground backwards through the base-emitter junction of the NPN TTL high output drive transistor, and in through pin 7 of the HCT153.  Running current backwards through the transistor's base-emitter junction risks destroying it, but I've never seen any of them damaged by this failure.  Replacing the diode has always been sufficient to repair the fault.  Possibly the most clear symptom of this fault is a low output voltage when using the pull-up source.  Because of its high output impedance, that source is generally effective at detecting current paths to ground.

 * U7, the LM346M providing gain for the VDAC output drivers.  I saw several of these fail together on a group of pin driver boards.  I don't know why.  The symptom was that if ramping the VDAC output voltage it would be fine up to some threshold and then plateau, and could not be raised above that voltage.  The fault was isolated by confirming the voltage driving the hybrid was ramping properly, the output was not, and there was no significant voltage drop across the base resistor for the LM395P on the pin driver board (confirming no excessive load on the op amp's output).
