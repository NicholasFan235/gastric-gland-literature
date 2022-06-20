# Chaste Crypt

## An integrative computational model for intestinal tissue renewal
- Gut epithelial layer renewed every few days (2-3 and 3-5 days mice and humans respectively)
- Computational model for renewal
- Non-fixed stem cell positions allows Monoclonal conversion and niche succession
- 20 million crypts in human large intestine
- Renewal driven by small number of stem cells at base of crypts of Lieberkuhn
- Stem cells proliferate occassionally -> 1 replacement stem cell and 1 semi-differentiated transit cell
- Transit cells then differentiate multiple times before terminal differentiation
- At crypt opening, mature cells are shed
- Wnt signalling maintains intestinal stem cell niche
- Position dependent proliferation rate determined by extracellular Wnt factors
- High Wnt -> inhibition of APC tumor suppressor -> high level $\beta$-catenin -> induced transcription of Wnt targets.
- $\beta$-catenin also responsible for cell-cell adhesion.
- Experimentally unconfirmed position and number of stem cells
- Unknown how cellular processes are regulated in crypt homeostasis
- Existing models on specific mechanisms (sub-cellular or macro-scale).
- Mutiscale model incorporating existing sub-cellular, cellular and macroscale components.
- Integrative approach. Each cell has continuum cell-cycle coupled to intracellular Wnt signalling model.
- Wnt Model
    - Intracellular gene expression
    - Intercellular adhesion potential
- Mechanical Model
    - Meineke et al.
    - Voronoi tesselation for size and neighbours. Neighbours connected by springs
    - Stem and transit cells divide, division direction stochastic.
    - Stem cells differentiate into replacement + transit. Transit cells undergo terminal differentation after fixed divisions.
    - No explicit cell death. Cells reaching top of crypt removed from simulation.
    - Displacement of cells due to mitotic pressure. Centres of cells attached by linear over damped springs.
    - Spring length starts at $L_0$, linearly increasing to $L$ during M phase. Remains constant after this.
- Wnt Signalling
    - Low to High Wnt from Top to Bottom of crypt.
    - Assume remains constant during stimulation. Cell only detects Wnt at its centre.
    - System of non-linear ODEs predicting temporal change in 10 components of Wnt pathway.
    - Used to quantify the levels of adhesion and transcription complexes in a cell
- Cell Cycle
    - Cell cycle model from Swat et al.
    - Includes Cyclin D, known Wnt target which with c-myc promotes $G_1/S$ transition ($\therefore$ proliferation.
    - Strong Wnt -> faster Cyclin D -> faster cell cycle.
- Cell-Cell and Cell-Matrix adhesion
    - Spring constant scaled by contact length
    - Also scaled by number of cell-cell adhesion complexes (cell with minimum complexes) to link to Wnt model.
    - For cell-matrix adhesion, damping term is scaled by cell surface area.
- Other
    - On division daughter cells placed $L_0/2$ away in opposite directions to conserve centre of mass.
    - Prevent cells moving off lower edge: If cell moves below edge, moved $0$-$0.05L$ above edge.
    - Whether cell differentiate after division is dependent on extracellular conditions.
- Limitations
    - Cell size uncontrollable (decided by voronoi tesselation). Daughter cell sizes may not sum to parent size. Cannot incorporate cell death (would cause unphysical change in neighbour cell sizes)
    - Crypt shape fixed to cylinder (overestimates number of stem cells in base)
    - Cannot account for crypt buckling (during fission or budding)
    - Neglected specialised differentiated cell types (especially paneth)


## A computational study of discrete mechanical tissue models
- Focusing on cell-centre models
- Two main aspects
    - Cell connectivity
    - Cell-cell interaction force
- Overlapping spheres or Voronoi tesselation
- Mentions energy approaches (metropolis algorithm). New cell position proposed and accepted depending on whether it reduces energy. (Outside scope of paper)
- Force laws:
    - Linear with cutoff (cutoff for 0 force at large distance)
    - Linear with exponential. (Exponential force increase at close distances to represent hard-core)
    - Hertz theory of contact
    - Johnson-Kendall-Roberts (JKR)
- Lack of robustness in overlapping spheres model
    - Allows connection of nearby cells through other cells
- Voronoi tesselation can cause anisotropy
- OS and Voronoi similar for elastic compression and yield stress. Identical results for tension and shear. Only different during plastic flow phase. OS much more efficient than Voronoi.


## A hybrid approach to multiscale modelling of cancer
- Detail in multiscale model allows experimental parameters to be incorporated
- Continuum models faster but hard to relate system parameters to measurable parameters.
- Compare cell-centre, cell-vertex and continuum model of cell proliferation
- Establish conditions under which mutant cells are able to colonize the crypt either via top-down or bottom-up invasion.
- Traditional PDE tumor growth models invalid on small number of cells. More experiments able to investigate individual cells $\therefore$ natural to produce models which can be validated at these levels
- Mutant vs normal cells have varying proliferation rate, cell-cell and cell-substrate adhesion properties. Healthy cells require Wnt signal to proliferate, mutants do not. Mutant cells have stronger adhesion.
- G1, S, G2 and M phases total duration sampled stochastically from normal distribution (mean 16h, s.d. 1h).
- Vertex Model
    - Equation for potential of each vertex.
    - Deformation energy (distance from target surface area)
    - Membrane surface tension (distance from target perimeter)
    - Cell-cell adhesion (depends on contact length)
    - On cell division parent is split along its short axis. Daughter cell target area linearly increases to mature cell target area over course of 1st hour. (from $\pi/8[d]^2$ to $py/4[d]^2$, $d$ is cell diameter)
- To study mutant invasion, introduce patch of mutant cells and investigate how varying adhesion or position changes ability to invade crypt.
    - Cell-vertex and continuum models suggest bottom-up is predominant method. But top-down is possible if adhesive effects are strong.

## Modelling spatially regulated $\beta$-catenin dynamics and invasion in intestinal crypts

## Comparing a discrete and continuum model of the intestinal crypt

## On an infrastructure to support sharing and aggregating pre- and post-publication systems biology research data

## A theoretical investigation of the effect of proliferation and adhesion on monoclonal conversion in the colonic crypt

## Mathematical modelling of monoclonal conversion in the colonic crypt

## A two-dimensional model of the colonic crypt accounting for the role of the basement membrane and pericryptal fibroblast sheath

## Modelling the role of the basement membrane in the colonic epithelium

