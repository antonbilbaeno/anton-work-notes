# Electrical Design Best Practices

## In General
- Ideal order of prototyping:
  1. Protoboard / breadboard
  2. PCB that is oversized and has lots of test points, LED indicators, easy to modify, etc.
  3. PCB designed for final shape
- sdf

## Soldering
### Lead-Free
- Crank it up to 750 deg F if you're using lead-free solder.

## Transistors
### Selecting A Transistor

## Antennas
### Antenna Checklist
- Verify ground planes have enough clearance with antenna.

## Schematic
### Checklist
1. Go through every signal and check if it will need a pull-up or pull-down
    - Consider different states for microcontroller and other ICs (e.g. sleep states)
### Protection
- Reverse voltage protection
  - PMOS: Drain & Source in series with V+, Gate goes to GND
  - Select a transistor that has extremely low RDS on
- Fuse
  - PTC resettable fuse:
    - Pay attention to the ratings
    - For example: a PTC may be rated to kick in at some voltage and 1A, but doesn't fully go into high impedance for some time after and current may peak at 2A
  - Hard Fuse
    - Types:
      - Standard: may require twice the rated current to open in 1 second
      - Fast-blow: may require twice the rated current to open in 0.1 seconds
      - Slow-blow: may require twice the rated current for tens of seconds to open
    - Voltage rating: make sure your fuse is rated at the appropriate voltage (plus de-rating). If it is not, it may arc and current will continue to flow
    
## Board
### Silkscreen
- Name of board
- Revision
### Panelization
- Always put odd shaped boards into rectangular shaped holders with mouse bites
  - Don't leave large air gaps (i.e. holes where there is no PCB) in the panel
    - This may cause your stencil to warp as you are applying paste and create bridges between solder pads
    
## Stencil
### General Tips
- It helps to place odd shaped boards in a rectangular panel
  - Don't leave any gaps in the PCB or surrounding PCB frame. As you are squeegeeing the paste, you may put pressure in a concentrated area and cause the stencil to warp.
    - When the stencil warps or bends it will cause pads to bridge
### Soldermask Between Pads
- Leave enough clearance between the stopmask layer of your pads. Even though you may have a gap in your design software, in real life you need minimum a ~6 mil width for it to be properly and reliably manufactured. Under 6 mil, you may get soldermask between some pads but not others. Check your manufacturer to figure out the tolerances.
### NSMD Pads (aka non-soldermask defined)
- Non solder mask defined means that the pad is... **not** defined by the solder mask. In other words, the size of the pad is defined by the copper layer. You create a _stop_mask area that is slightly bigger than the copper area of the pad. This creates a very small gap between where the solder mask ends and where the copper begins, and so the final size of the pad is defined by the copper iself.
  - This is significant because the etching process for the copper has tighter tolerances than the solder mask process.
    - In contast to a solder mask defined pad, where the copper area is bigger than the stopmask, and the soldermask creeps in slightly on top of the copper.
  - When you create NSMD pads, you know the size will be very close to exactly as you defined it in the software.
### ...versus SMD Pads (aka soldermask defined)
- If the process on the copper etch is more accurate, why would we ever want to define the exposed area for soldering any other way?
  - SMD pads are commonly used for the exposed pad or thermal pad underneath surface mount chips.
  - Since the soldermask slightly creeps over on top of the copper, it creates a slightly stronger pad.
    - Since the surface tension from the solder will be stronger on the thermal pads (because they are larger), this helps prevent the pad itself from being lifted.
  - Defining the pad by the soldermask also prevents the thermal pad from shorting out to the perimeter pads. It acts as a wall that holds the solder in towards the middle.


# EAGLE CAD Tips and Trickz
## Schematic
### Renumbering Parts
- From the schematic view:
  - Go to... Tools -> Renumber parts...
    - I prefer to change the "Weighting of emphases" to Y-direction.
      - I leave everything else the same.
      - This will renumber your parts going from the top left corner and then across to the right side, then move down, and repeat.

### Normalizing Silkscreen
- Sunstone's min. silkscreen width is 6mil.
  - Forget about the size of your text, the %, ratio, or whatever.
  - When you zoom in on that ish, set your grid to 3mil. If the width of your text doesn't take up two grid squares, it's not big enough.
    - You might be able to get away with less, but this is what they spec and is also what is easily readable with the human eye.
- There is a ULP to smash (the function that lets you move text associated with a package) and re-size all of your text automatically.
  - From the board view:
    - Go to File -> Run ULP.
      - Start typing "normalize" and select the normalize-text.ulp
      - To get a 6mil width:
        - Output units: mm
        - Text size: 1
        - Text thickness: 0.15
- This size also fits perfectly on a 0.5mm grid, so if you're using this size grid for placing components, then it works out great. Especially for 0402 components which you can place side by size on a 0.5mm grid.

## Dimensioning
- Sometimes you may want to manually dimension something on the 'finest' grid.
  - This may be due to Eagle trying to snap to certain objects.
  - If you hold Ctrl before clicking your first point (while using the finest grid), you can do so.
    - However, Eagle may try to snap to the grid or an object for your second point.
    - Just swing your mouse around (while holding Ctrl) for a while until it stops trying to snap.

## Hotkeys


## ULPs


## DRC


## ERC


ZJQ24-35F580C

