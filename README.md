# KiCad Model of Logical Devices' ALLPRO88 Pin Driver Hybrid Module

This provides a KiCad schematic of the pin driver hybrid modules used in Logic Devices' ALLPRO88 software-driven device programmer.  The service manual scans available on the internet are missing the pages containing the pin driver circuitry.  I have traced out some of my own and guessed at what the SMD parts might be based on their markings and electrical properties.  I believe the schematic is correct, it's certainly correct enough for me to have repaired many of these modules based on what's here, but I found errors as recently as the fall of 2024 so I wouldn't say it's definitely correct.  Your mileage might vary.

There is a PCB layout, but it's not meant to be used to make actual hybrid modules, it's only meant to help with debugging.  There are no traces or mounting pins.  Only the SMD components are placed in their approximate locations.  The resistors (which in the real hybrids are integrated directly into the traces) are mostly not placed properly at all.  Also, there are several revisions of the hybrid module, I have a mix of several in my own units myself, and the parts placement only matches one of them (I think the oldest version).  Good enough for me.

See also https://github.com/cannon-zz/allpro88-pin-driver.
