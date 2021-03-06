# Gagnon VAN Data Set

## Background
This folder contains the microvascular angiograms that were collected around 2010 by 
Boas and Sakadzic at MGH. that were then subsequently graphed and used in VAN modeling of the fMRI BOLD signal
and published in Gagnon2015, Gagnon2016, and Cheng2019.

Each folder contains the raw angiogram of the cerebral vascular network of a mouse acquired by two photon microscopy. Details of the acquired raw angiogram are in Gagnon2015, excerpted here:

> All experimental procedures were approved by the Massachusetts General Hospital Subcommittee on Research Animal Care. We anesthetized C57BL/6 mice (male, 25–30 g, n=6) by isoflurane (1–2% in a mixture of O2 and air) under constant temperature (37 °C). A cranial window with the dura removed was sealed with a 150-μm-thick microscope coverslip. During the experiments, we used a catheter in the femoral artery to monitor the systemic blood pressure and blood gases and to administer the two-photon dyes. During the measurement period, mice breathed a mixture of O2, and air under the 0.7-1.2% isoflurane anesthesia. Imaging was performed using a custom built two-photon microscope (Sakadžić et al., 2010) and two-photon enhanced oxygen sensitive phosphorescent dye PtP-C343 (Finikova et al., 2008). The time-domain measurements of phosphorescence lifetimes were performed following the procedures outlined in (Sakadžić et al., 2010; Devor et al., 2011; Parpaleix et al., 2013). Approximately 400 pO2 measurements were collected in various microvascular segments down to 450 µm from the cortical surface. The conversion between pO2 and oxygen saturation of hemoglobin (SO2) was performed using the Hill equation with Hill coefficients specific for C57BL/6 mice (h = 2.59 and P50 = 40.2) (Uchida et al., 1998).

> After collecting the pO2 measurements, we obtained structural images of the cortical vasculature by labeling the blood plasma with dextran-conjugated fluorescein (FITC) at 500nM concentration. We acquired 600 x 600 x 662 um stacks of the vasculature with 1.2 x 1.2 x 2.0 μm voxel sizes under a 20X Olympus objective (NA=0.95). 


## Files
Each sub-directory contains a raw angiogram and graphs from one mouse. The angiogram is a TIF file and the dimensions of the volume are indicated in the file name. The graphs have been generated by different procedures described below. We also have the "ground truth" graph that was generated for Gagnon2015 by human manual correction of a graph generated by the VIDA method. 

All graph files are matlab files. Each matlab file contains a data structure *Graph* with fields *Graph.nodes* and *Graph.edges*. *Graph.nodes* is an nx3 matrix representing the 3D position of the n graph nodes. *Graph.edges* is an mx2 matrix representing the 2 indices of the graph nodes for each of the m edges in the graph.


## Graphing Methods

VIDA - The [VIDA](https://neurophysics.ucsd.edu/software.php) method was developed by David Klienfield's Laboratory at UC San Diego. More details about the software can be obtained in the publication [Tsai et al](http://www.jneurosci.org/content/29/46/14553.short).

Walle - This method uses 3D Deep Learning for vessel segmentation and then extracts the graph from segmentation. The 3D deep learning method is being developed by [Lei Tian's](http://sites.bu.edu/tianlab/) group in collaboration with the [Boas Lab](http://sites.bu.edu/boas/) at Boston University. Graph extraction from the segmented was developed by [Frederic Lesage's](http://image.liom2.polymtl.ca//en/home) group at Université de Montréal in Montreal. More details about the graph extraction software can be found in the publication [Damseh, Rafat, et al](https://ieeexplore.ieee.org/abstract/document/8555544).


## Citations

Gagnon, L., Sakadžić, S., Lesage, F., Musacchia, J.J., Lefebvre, J., Fang, Q., Yücel, M.A., Evans, K.C., Mandeville, E.T., et al., “Quantifying the microvascular origin of BOLD-fMRI from first principles with two-photon microscopy and an oxygen-sensitive nanoprobe.,” The Journal of neuroscience : the official journal of the Society for Neuroscience 35(8), 3663–3675 (2015).

Gagnon, L., Sakadžić, S., Lesage, F., Pouliot, P., Dale, A.M., Devor, A., Buxton, R.B., and Boas, D.A., “Validation and optimization of hypercapnic-calibrated fMRI from oxygen-sensitive two-photon microscopy.,” Philosophical transactions of the Royal Society of London. Series B, Biological sciences 371(1705), 20150359 (2016).

Cheng, X., Berman, A.J.L.J., Polimeni, J.R., Buxton, R.B., Gagnon, L., Devor, A., Sakadžić, S., and Boas, D.A., “Dependence of the MR signal on the magnetic susceptibility of blood studied with models based on real microvascular networks.,” Magnetic resonance in medicine (2019).

