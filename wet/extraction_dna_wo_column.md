## Protocol for DNA extraction of long fragments for nanopore sequencing

based on a protocol [posted by Nick Loman](http://lab.loman.net/2017/03/09/ultrareads-for-nanopore/) and used in:

Jain, Miten, Sergey Koren, Josh Quick, Arthur C. Rand, Thomas A. Sasani, John R. Tyson, Andrew D. Beggs, et al. 2017. “Nanopore Sequencing and Assembly of a Human Genome with Ultra-Long Reads.” bioRxiv. doi:10.1101/128835.

- [version 1.3](https://docs.google.com/document/d/1ITV4XobY0GQ0m-pBlhIUqvhuSJBIgoWVHS1av4e4XIk/edit)
- [version 1.2](https://docs.google.com/document/d/1025Tu_zPWqK14JEJ9IFzRul1l5RoIORE_FcAUrQpMwA/edit)

The protocol is a mixture of Quick et al. and the mouse-tail lysis protocol from the FLI.

### Cells

Currently tested on E. coli (TOP10 F) cell lines.

### Modifications

- 15 min into lysis, vortex 30 sec (w/ glass beads?)
- follow Quick et al. to the letter
- lysin cocktail for gram+ (from MARC3 protocol, "PW" .. power water buffer)
- sonification

### Buffers

TLB (from long-fragment protocol v1.2 by Quick et al.):

| reagent | unit |
| ------------- | ------------- |
| Tris-Cl  | 10 mM, pH 8.0  |
| EDTA  | 25 mM, pH 8.0  |
| SDS  | 0.5 % (w/v)  |
| RNase A | 20 µg/ml (QIAGEN, add fresh just before use) |

// TODO: add proteinase K? Quick et. al write:

> Add Qiagen Proteinase K (20 mg/mL) to a final concentration of 200 ug/ml.

EB (from long-fragment protocol v1.3 by Quick et al.):

10 mM Tris-Cl pH 8, 0.05% Triton X-100

// Why Triton-X?

> Thermo MuA buffer contains Triton X-100, we've found adding it improves efficiency of the library. -- Josh Quick, comment on protocol v1.3

### Procedure

- take an overnight culture of E. coli growing LB medium
- dilute E. coli culture with LB to desired OD (0.8 at 600 nm) ad 25 ml
// OD measured on a NanoDrop 2100 w/ program "Cell Culture" using a cuvette

- spin(g=4.5, time=10, degrees=4, unit='celsius')
- resuspend pellet by pipette mixing in 100 µl sterile PBS
// PBS is used to buffer the lysed solution (additionally to Tris buffer)
// pellet needs to be resuspended well, otherwise less surface for lysis to act upon
// water not good, bc/ not buffered, will reduce buffer abilities

- add 10 ml TLB
- vortex at full speed for 5 seconds
// will foam, which is not a problem

- incubate at 37°C for 1 hour
// so that cells grow a little more? membrane thins -- lysis more effective

- mix by slowly rotating end-over-end 10 times
- incubate at 50°C over night in water bath
- precipitation:
  - add 2 ml NaCl (5 M)
  // Why is salt added before spin? This is called ["salting out"](https://en.wikipedia.org/wiki/Salting_out), which means that proteins are precipitated [in presence of large salt concentration](https://en.wikipedia.org/wiki/Ammonium_sulfate_precipitation). If not performed in this order, a mucous plug forms, from which the DNA will not readily precipitate.
  - invert 10 times
  - spin(max, 10, 4)
  // removes crap
  - prepare falcon tube containing 7.74 ml isopropanol
  // ratios?
  - transfer 12 ml supernatant from spin

- alternative (from Quick et al.):
  - add 4 ml 5 M ammonium acetate
  - add 30 ml ice-cold ethanol and rotate gently end-over-end 10 times
  // more generally: 2.5 vol. 96 % ethanol, 0.1 vol. 5 M ammonium acetate
  // any saturated salt will do
  // can be done at -20/ -80 °C overnight (the lower the slower the more gentle)
  // isopropanol is a "stronger" alcohol than ethanol and binds 2 times the water
  // [on isopropanol precipitation](http://www.chemieonline.de/forum/showthread.php?t=163467)
  - make a hook by melting a glass capillary in a blue flame
  - ...

- invert 25 times (super gentle)
- spin(max, 10, 4)
- discard supernatant
- add 4 ml 70 % ethanol
// this is the wash step
// try not to disturb pellet -- if pellet moves, spin again

- remove ethanol
// do not decant, but pipette the ethanol off

- air dry pellet (> 10 min)
- dissolve DNA in 150 µl nuclease free water or TE
// do not pipette, mix by flicking the tube

- resuspend pellet:
  - incubate at 55 °C for 1-3 h
  // optional, e.g. from NucleoBond (MageryNagel) and G-Tip (QIAGEN) protocols
  - incubate at 4°C or room temperature overnight


