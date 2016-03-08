$include(metadata.yaml)

$include(theme.yaml)

#### $titlepage
---
overtheme:
  - slide:
    - data-scale: '10'
    - border-top-right-radius: '100px'
    - border-bottom-right-radius: '500px'
    - content:
      - border-top-right-radius: '100px'
      - border-bottom-right-radius: '500px'
      - padding: '0%'
---

$box
$style[border-top-left-radius:0%;
       border-top-right-radius:100px;
       border-bottom-right-radius:0px;
       width:100%;
       margin-left:0%;
       margin-top:0%;
       height:30%;
       background:#4788B3;
       font-family:'Comic Sans MS', cursive, sans-serif;]
$content[width:95%;
         color:white;
         text-align:center;]{
$title[display:block;
       font-size:140%;
       padding-top:3%;
       padding-bottom:3%;
       padding-right:2%;]
$logo[margin-left:55%;height:50px;]
}
$endbox

$columns

$column[width:45%;]

$figure
$content[width:90%;
         padding-top:3%;
         box-shadow: 7px 7px 5px rgba(200,200,200,0.0);]{figures/atena.jpg}
$caption(None){}
$endfigure

$column[width:55%;]

$box
$style[width:100%;
       padding-top:2%;
       font-family:'Comic Sans MS', cursive, sans-serif;]
$content[text-align:center;
         color:#4788B3;]{
$conference[display:block;
            font-size:130%;
            padding-right:10%;
            padding-top:5%;]
$location[display:block;
          font-size:80%;
          text-align:right;
          padding-right:10%;
          padding-top:5%;]
$date[display:block;
      font-size:80%;
      text-align:right;
      padding-right:10%;]
}
$endbox

$endcolumns

<p></p>
$box
$style[width:100%;
       font-family:'Comic Sans MS', cursive, sans-serif;]
$content[text-align:left;padding-left:1%;]{
a presentation by $authors[display:block;font-size:110%;color:#4788B3;]
<p></p>
<p></p>
$emails[display:block;font-size:80%;padding-right:2%]
<p></p>
<p></p>
$affiliations[display:block;font-size:100%;padding-left:5%]
}
$endbox

### CFD at CNR-INSEAN

#### CFD at CNR-INSEAN
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '14100'
    - data-y: '-3000'
---

$columns

$column[width:30%]

$note
$caption(none){Applications}
$content{
Fluid dynamic studies concerning complex-shaped moving bodies for:

+ Hydrodynamics:
    + resistance;
    + manoeuvrability and stability;
    + propellers/appendages/hulls interactions;
    + sea--keeping.
    + underwater noise;
    + multiphase flows.
+ aerodynamics:
    + airplanes;
    + wind turbines.
    + aerospace launchers;
}
$endnote

$figure
$caption(None)[position:TOP;font-size:110%]{Manoeuvrability}
$content[width:220%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm00.png}
$endfigure

$column[width:30%]

$figure
$caption(None)[position:TOP;font-size:110%]{Propulsion}
$content[width:140%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop11.png}
$endfigure

$figure
$caption(None)[position:TOP;font-size:110%]{Renewable Energy}
$content[width:140%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/bt2-01.png}
$endfigure

$column[width:30%]

$figure
$caption(None)[position:TOP;font-size:110%]{Gas Dynamics}
$content[width:160%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/vega/vega.png}
$endfigure

$endcolumns

#### Xnavis CFD solver
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '14100'
    - data-y: '-2200'
---

$note
$caption(none){Xnavis Code Features}
$content{
Xnavis is an in-house (Fortran language, standard 95) fluid dynamics code solver
}
$endnote

<p></p>

$columns

$column[width:50%;font-size:90%]

$note
$caption(none){Modeling features 1/2}
$content{}
$endnote
<p></p>

+ Solver based on the Unsteady Navier-Stokes Equations:
    + Reynolds Averaged Equations, **RANS**;
    + **LES** Filtered Equations;
    + **DES** (and **DDES**) Equations.
+ finite volume formulation, co-located cell centred;
+ spatial discretization:
    + convection and pressure:
        + second order **ENO**-type (Harten et al., 1987);
        + third order upwind biased (van Leer, 1979);
        + third order **WENO**-type (Liu et al., 1994; Jiang et al., 1996);
        + fourth order centred.
    + viscous terms: second order centred.
+ time integration by second order implicit scheme (three points backward);
+ solution at each time step: pseudo-time integration (Chorin, 1967; Merkle 1987):
    + Euler implicit with approximate factorization (Beam $\&$ Warming, 1978);
    + local pseudo time step, multi-grid acceleration.
+ turbulence model: algebraic, one-equation and two-equations, LES, DES.
+ propeller model:
    + non interactive Hough $\&$ Ordway (nominal wake);
    + interactive RANS/BEM coupling  (effective wake);
    + direct simulation of the propeller (No Model).
+ single and two-phase level set approach for free surface;

$column[width:50%]

$note
$caption(none){Modeling features 2/2}
$content{}
$endnote
<p></p>

+ dynamic overlapping grids;
+ multiple bodies 6 D.O.F. dynamics;
+ multi--paradigms parallelization:
    + OpenMP paradigm for shared memory architectures;
    + Message Passing Interface (MPI) paradigm for distributed memory architectures;
    + OpenMP/MPI mixed paradigm for large distributed cluster of SMP nodes.

$note
$caption(none){Ongoing and Future Developments}
$content{}
$endnote
<p></p>
+ adaptive mesh refinement (AMR);
+ automatic dynamic control;
+ interior noise prediction and control with smart dynamics solver and LQR optimal control;
+ HPC enhancement: automatic load balancing for thousands of processors with huge mesh size;
+ cavitation models (barotropic and mass transfer ones);
+ two--way, fully coupled, unsteady hydro--elasticity models (one--way steady model already implemented);
+ ...

$endcolumns

#### Original in-house Chimera scheme
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '14100'
    - data-y: '-1400'
---

$note
$caption(none){Chimera scheme}
$content{Xnavis is supplemented with an original, in-house developed chimera approach that is based on a body-force like interpolation between overlapping grids. This scheme is robust and effective and it allows high quality spatial discretization of very complex-shaped bodies even in relative motion.}
$endnote

$columns

$column[width:30%]

$figure
$content[width:135%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm05.png}
$caption(None){}
$endfigure

$figure
$content[width:135%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm07.png}
$caption(None){}
$endfigure

$figure
$content[width:135%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm08.png}
$caption(None){}
$endfigure

$column[width:65%]

$video
$content[margin-top:10%;width:90%;;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{videos/rudder.m4v}
$caption(none){Dynamic Chimera Grids}
$endvideo

$endcolumns

### Hydrodynamics Experiments

#### Propulsion: Propeller with axial inflow
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '14050'
    - data-y: '-600'
---

$note
$caption(none){Simulation Details}
$content{DES simulations of E779A propeller in open water with axial inflow in open water characteristics}
$endnote

$columns

$column[width:33%]

$figure
$content[width:110%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop7.png}
$caption(None){}
$endfigure

$column[width:33%]

$figure
$content[width:110%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop8.png}
$caption(None){}
$endfigure

$column[width:33%]

$figure
$content[width:110%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop9.png}
$caption(None){}
$endfigure

$endcolumns

$columns

$column[width:50%]

High value of angular velocity. High turbulence generation.

$figure
$content[width:110%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop11.png}
$caption(None){}
$endfigure

$column[width:50%]

Low value of angular velocity. Low turbulence value.

$figure
$content[width:110%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop12.png}
$caption(None){}
$endfigure

$endcolumns

#### Propulsion: Propeller beneath the free-surface
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '13900'
    - data-y: '200'
---

$note
$caption(none){Simulation Details}
$content{uRaNSe simulations of E779A propeller in open water with non axial inflow beneath the free-surface}
$endnote

$columns

$column[width:55%]

$figure
$content[width:90%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop17.png}
$caption(None){}
$endfigure

$figure
$content[width:90%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop18.png}
$caption(None){}
$endfigure

$column[width:45%]

$figure
$content[width:90%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop19.png}
$caption(None){}
$endfigure

$figure
$content[width:90%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/prop/prop20.png}
$caption(None){}
$endfigure

$endcolumns

#### Maneuvering: Free Running of Tanker-Like Model 1/2
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '13600'
    - data-y: '1000'
---

$columns

$column[width:48%;margin-right:2%]

$note
$caption(none){Aims}
$content{Two different configurations, single and twin rudders:

+ assessment of the capabilities of the CFD solver;
+ analysis of the manoeuvring characteristics of the two models;
+ analysis of the flow field.
}
$endnote

<p></p>

$figure
$content[width:105%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/turningcirc/tc-04.png}
$caption(None){}
$endfigure

$column[width:50%]

$note
$caption(none){Main Dimensions}
$content{Twin rudder plus skeg configuration: a total of about 7.8M of finite volumes distributed in 282 blocks.

For the free surface refinement there are 2 blocks for a total of 2M of finite volumes, for the hull there are 18 blocks with 2.7M volumes and for the rudders there are 208 blocks with 2.2M volumes.
}
$endnote

<p></p>

$figure
$content[width:105%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/turningcirc/tc-05.png}
$caption(None){}
$endfigure

$endcolumns

#### Maneuvering: Free Running of Tanker-Like Model 2/2
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '13200'
    - data-y: '1800'
---

$video
$content[margin-top:1%;width:95%;]{videos/turncir.m4v}
$caption(none){Trajectory of Turning Cirle Manouvre}
$endvideo

#### Captive Tests of Submarine 1/2
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '12500'
    - data-y: '2600'
---

$columns

$column[width:18%]

$figure
$content[height:4cm;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm01.png}
$caption(None){}
$endfigure

$column[width:54%]

$figure
$content[height:4cm;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm04.png}
$caption(None){}
$endfigure

$column[width:26%]

$figure
$content[height:4cm;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm03.png}
$caption(None){}
$endfigure

$endcolumns

$columns

$column[width:25%]

$figure
$content[width:120%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm05.png}
$caption(None){}
$endfigure
$figure
$content[width:120%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm07.png}
$caption(None){}
$endfigure

$column[width:25%]

$figure
$content[width:120%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm06.png}
$caption(None){}
$endfigure
$figure
$content[width:120%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/subm08.png}
$caption(None){}
$endfigure

$column[width:50%]

$note
$caption(none){SUBMOTION II Project}
$content{
+ European Defense Agency (EDA) project:
    + strong collaboration of:
        + Italian and Norwegian Navy;
        + CNR-INSEAN and MARINTEK Institute;
+ aims:
    + assessment of the capabilities of the CFD solver;
    + analysis of the manoeuvring characteristics of two submarine configurations;
    + improve the overall confidence on prediction tools employed;
}
$endnote

$endcolumns

#### Captive Tests of Submarine 2/2
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '11450'
    - data-y: '3300'
---

$columns

$column[width:50%]

$figure
$content[width:100%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/pitch/p_m14deg-x-slice-u-fore.png}
$caption(None)[position:TOP]{Pitch submarine 12 deg, canard angle of attack 0 deg}
$endfigure

$figure
$content[width:100%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/pitch/p_m14deg-x-slice-u-stern.png}
$caption(None)[position:TOP]{Pitch submarine 12 deg, canard angle of attack 0 deg}
$endfigure

$column[width:50%]

$figure
$content[width:100%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/pitch/p_m12deg-c_m10deg-x-slice-u-fore.png}
$caption(None)[position:TOP]{Pitch submarine 12 deg, canard angle of attack -10 deg}
$endfigure

$figure
$content[width:100%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/subm/pitch/p_m12deg-c_m10deg-x-slice-u-stern.png}
$caption(None)[position:TOP]{Pitch submarine 12 deg, canard angle of attack -10 deg}
$endfigure

$endcolumns

#### Free surface flow: fast catamarans 1/2
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '10400'
    - data-y: '3800'
---

Catamaran advancing in steady drift *6deg*, *Fr=0.4*

$columns

$column[width:40%]

$note
$caption(none){NICOP Catamarans}
$content{

+ Office of Naval Research (US Navy) project:
    + strong collaboration of:
        + IIHR-Hydroscience and Engineering of University of Iowa;
        + CNR-INSEAN;
+ aims:
    + gain more insight into the knowledge of the hydrodynamics of fast catamaran vessels;
    + construct a valuable data set for CFD benchmarking;
    + sea keeping behavior and operation in off design conditions (static large drift conditions);
}
$endnote

$column[width:60%]

$figure
$content[width:90%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/cat/cat4.png}
$caption(None){}
$endfigure

$figure
$content[width:90%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/cat/cat5.png}
$caption(None){}
$endfigure

$figure
$content[width:90%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/cat/cat6.png}
$caption(None){}
$endfigure

$endcolumns

####  Free surface flow: fast catamarans 2/2
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '9350'
    - data-y: '3950'
---

$video
$content[margin-top:1%;width:85%;]{videos/cat.m4v}
$caption(none){Fast catamaran in steady drift}
$endvideo

$columns

$column[width:50%]

$figure
$content[width:80%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/cat/cat2.png}
$caption(None){Stereo PIV}
$endfigure

$column[width:50%]

$figure
$content[width:80%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/cat/cat3.png}
$caption(None){CFD}
$endfigure

$endcolumns

### Aerodynamics Experiments

#### Renewable Energy: Horizontal Axis Wind Turbine 1/2
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '8300'
    - data-y: '3950'
---

$columns

$column[width:50%]

$note
$caption(none){Wakebench Project}
$content{

+ framework:
    + International Energy Agency (IEA) Co-operation;
+ aims:
    + validate Xnavis for Renewable applications;
    + reproduce NTNU blind tests experiments:
        + model scale Horizontal Axis Wind Turbine performances and flow feattures (wakes);
        + farm of model scale Horizontal Axis Wind Turbine;
        + relevant blockage effects;
}
$endnote

$column[width:50%]

$figure
$content[width:120%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/bt2-01.png}
$caption(None){}
$endfigure

$endcolumns

$columns

$column[width:50%]

$figure
$content[width:85%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/bt2-07.png}
$caption(None){}
$endfigure

$column[width:50%]

$figure
$content[width:85%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/bt2-08.png}
$caption(None){}
$endfigure

$endcolumns

#### Renewable Energy: Horizontal Axis Wind Turbine 2/2
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '7250'
    - data-y: '3950'
---

$columns

$column[width:32%]

$figure
$content[width:140%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/alpha-vorticity-side-view-l1.png}
$caption(None){}
$endfigure

$figure
$content[width:140%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/alpha-vorticity-side-view-l7.png}
$caption(None){}
$endfigure

$column[width:32%]

$figure
$content[width:140%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/alpha-vorticity-side-view-l3.png}
$caption(None){}
$endfigure

$figure
$content[width:140%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/alpha-vorticity-side-view-l9.png}
$caption(None){}
$endfigure

$column[width:32%]

$figure
$content[width:140%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/alpha-vorticity-side-view-l5.png}
$caption(None){}
$endfigure

$figure
$content[width:140%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/bt2/alpha-vorticity-side-view-l11.png}
$caption(None){}
$endfigure

$endcolumns

#### External Aerodynamic Heating of Vega Launcher
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '6200'
    - data-y: '3850'
---

$columns

$column[width:50%;font-size:90%]

$note
$caption(none){European Space Agency Collaboration}
$content{

+ aims:
    + validate Xnavis for compressible applications;
    + reproduce the Vega Launcher aerodynamic heating;
        + termical loads on stages connectors;
}
$endnote

$column[width:50%]

$figure
$content[width:120%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/vega/vega01.png}
$caption(None){}
$endfigure

$endcolumns

$columns

$column[width:50%]

$figure
$content[width:80%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/vega/vega08.png}
$caption(None){}
$endfigure

$figure
$content[width:80%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/vega/vega09.png}
$caption(None){}
$endfigure

$column[width:50%]

$figure
$content[width:80%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/vega/vega10.png}
$caption(None){}
$endfigure

$figure
$content[width:70%;box-shadow: 7px 7px 5px rgba(0,0,0,0.0)]{figures/vega/vega11.png}
$caption(None){}
$endfigure

$endcolumns

#### Gas Dynamics
---
overtheme:
  - copy-from-theme: True
  - slide:
    - data-scale: '1'
    - data-x: '5150'
    - data-y: '3450'
---

$columns

$column[width:25%]

$note
$caption(none){OFF, a new CFD Solver}
$content{

+ aims:
    + compressible flows;
    + multi-specie flows;
    + multi-phase flows;
    + very high-order methods;
    + adaptive mesh refinement;
+ free;
+ OOP;
+ modern Fortran;

}
$endnote
<p></p>
<p></p>
<p></p>
<p></p>
##### https://github.com/szaghi/OFF

$column[width:75%]

$video
$content[margin-top:0%;width:95%;]{videos/ujt.m4v}
$caption(none){Strongly Under-Expanded Jets Transient}
$endvideo

$endcolumns
