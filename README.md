# Universal-Effective-Medium-Theory

<div align="justify">
 
The ability to tune phonon transport through nanoscale engineering holds promises for thermal management and energy conversion applications. At the nanoscale, phonon-mediated thermal transport significantly deviates from the bulk diffusive scheme. Therefore, predicting thermal conductivity in the non-diffusive regime requires models, such as the Boltzmann transport equation (BTE), that capture phonons' size effects. Although the BTE is robust and has been well validated against several key experiments, its applicability is computationally expensive. Thus, several analytical models have been put forward to estimate the effective thermal conductivity in low length scales. These methods are mostly based on simplified material descriptions such as gray-medium approximation; Assuming mean-free-path (MFP) independent population of phonons leads to an inaccurate description of phonons' behavior in nanostructured materials. To fill this gap, we developed the reduced-order closed-form ''Ballistic Correction Model'' (BCM) that takes into account the whole spectrum of MFP distribution and describes the reduction in thermal conductivity due to the size effects with effective Knudsen number. We used the BCM model to compute the thermal conductivity of thin films, nanowires, and bulk materials with nanoscale porosity. We validate our approach, against BTE-informed simulations, obtaining excellent agreement. Providing a simple yet accurate estimation of thermal transport in thin films, our work sets out to accelerate the discovery of materials for energy-conversion and thermal-management applications.
  
 </div>
 
- [Theory](#Theory)
- [Model Validation](#Model-Validation)
- [Phonon Bandpass Filtering in Bulk Alloys with Nanoscale Porosity](#Phonon-Bandpass-Filtering-in-Bulk-Alloys-with-Nanoscale-Porosity)
- [Characteristic MFP of Alloys](#Characteristic-MFP-of-Alloys)
- [Lattice Thermal Conductivity](#Lattice-Thermal-Conductivity)
- [Tables of the Lattice Thermal Conductivity Charractristic MFP in Dielectrics and Diffusive Suppression for Pores with Different Shapes and Porosity](#Tables-of-the-Lattice-Thermal-Conductivity-Charractristic-MFP-in-Dielectrics-and-Diffusive-Suppression-for-Pores-with-Different-Shapes-and-Porosity)


# Theory

 <p>
To begin, we lay out the theoretical basis for the Ballistic Correction Model (BCM). The starting point of the BCM model is to approximate the normalized cumulative thermal conductivity as 
<p align="center">
<img src="https://latex.codecogs.com/png.latex?%5Cdpi%7B100%7D%20%5Calpha%28%5CLambda%29%20%3D%20%5Cfrac%7B1%7D%7B%5Ckappa_%7B%5Cmathrm%7BBULK%7D%7D%7D%5Cint_0%5E%5CLambda%20K%28%5CLambda%27%29%20d%5CLambda%27%5Capprox%20%5Cleft%5B1&plus;%5Cfrac%7B%5CLambda_0%7D%7B%5CLambda%7D%5Cright%5D%5E%7B-1%7D" align="center" alt="drawing">
</p>
and 
<p align="center">
<img src="https://latex.codecogs.com/png.latex?%5Cdpi%7B100%7D%20S%28%5CLambda%29%5Capprox%20S%280%29%5Cleft%5B1&plus;%5CLambda/L_w%20%5Cright%5D%5E%7B-1%7D" align="center" alt="drawing">
</p>

These logistic function approximations (on a log scale abscissa) hold for most of materials and simple geometries. Here, ??<sub>o</sub> is the characteristic MFP showing the medium MFP of phonon distribution, L<sub>w</sub>_w is the average phonon line-of-sight to the geometric centers and S(0) is the macroscopic suppression function equal to S(0) = ??<sub>f</sub>/??<sub>b</sub>, where ??<sub>f</sub> is the Fourier's prediction of the effective thermal conductivity. The BCM model predicts:
<p align="center">
<img src="https://latex.codecogs.com/png.latex?%5Cdpi%7B100%7D%20%5Ckappa_%7B%5Cmathrm%7BFILM%7D%7D%20%3D%20%5Ckappa_%7B%5Cmathrm%7BBULK%7D%7D%5CXi%28Kn%29" align="center" alt="drawing">
</p>
where the correction term, ??, that accounts for truncation of long MFP phonons, is given by
<p align="center">
<img src="https://latex.codecogs.com/png.latex?%5Cdpi%7B100%7D%20%5CXi%20%28Kn%29%20%3D%20%5Cleft%5B%5Cfrac%7B1%20&plus;%20Kn%20%5Cleft%28%20%5Cln%28Kn%29%20-%201%20%5Cright%29%7D%7B%5Cleft%20%28%20Kn%20-%201%20%5Cright%29%5E2%7D%20%5Cright%5D" align="center" alt="drawing">
</p>
with the Knudsen number Kn=??<sub>o</sub>/L<sub>w</sub>. For Kn = 1, we have ??<sub>FILM</sub> = 1/2??<sub>BULK</sub>. For Kn ??? 0, ?? ??? 1, recovering the diffusive regime. For large Kn, i.e., in the ballistic regime, ?? ??? Ln(Kn)/Kn.
</p>
<p align="center">
<img src="Kn.png" align="center" alt="drawing" width="700px"> 
</p>

# Model Validation

The Boltzmann transport equation (BTE) is a robust mathematical tool to conceive thermal conductivity in the (non)diffusive regime. Thus we validated the BCM model against a set of simulations performed using the BTE solver AlmaBTE.~\cite{carrete2017almabte} The development and validation of AlmaBTE with experimental data have been established in the literature through a series of publications over the last years. The phonon dispersions and the scattering rates were computed on at least a 30 by 30 by 30 points Brillouin zone mesh sampling; the second and third-order interatomic force constants for bulk materials, computed with density functional theory and using the virtual crystal approximation, are obtained from the AlmaBTE materials database.

<p align="center">
<img src="Validation/kappa.png" align="center" alt="drawing" width="700px"> 
</p> 

<p align="center">
<img src="Validation/kappa_predic_alloys.png" align="center" alt="drawing" width="700px"> 
</p> 

<p align="center">
<img src="Validation/kappa_predic.png" align="center" alt="drawing" width="700px"> 
</p> 

<p align="center">
<img src="Validation/kappa_predic_crossplane.png" align="center" alt="drawing" width="700px"> 
</p> 

# Phonon Bandpass Filtering in Bulk Alloys with Nanoscale Porosity

The lattice thermal conductivity of alloys is generally determined by a combination of phonon-phonon Umklapp and mass disorder scatterings. The three-phonon scattering processes strongly rely on stiffness matrix and anharmonic bonding, while the mass disorder relies on the difference in the atomic mass of compounds. The mass mismatch strongly scatters phonons with short wavelengths near the Brillouin zone edge with negligible detriment to phonons with long wavelengths near the center of the Brillouin zone. The additive nanoscale porosity limits propagation of long-MFP phonons near the Brillouin zone center, thus, alloys with nanoscale porosity imprint ultra-low thermal conductivity and suppressed phonons distribution across the frequency spectrum. Thus, the central strategy behind the phonon's band-pass filtering is to selectively scatter phonons within specific frequency ranges. Following figures show band-pass filtering through additive point defect alloys and nanoscale porosity in AlAs from first-principles calculations. High-frequency low-wavelength optical phonons are completely filtered out and the acoustic phonons (except for the ones near the Brillouin zone center) are strongly suppressed due to mass-disorder scattering. The reduction in thermal conductivity exceeds 90%. More than 70% reduction in lattice thermal conductivity through filtering long-MFP short-wavelength phonons is observed. As aforementioned, long-wavelength phonons do not see the pores in bulk AlAs with ?? = 0.25 and L = 100 nm. Phonons across the whole frequency spectrum are strongly suppressed leading to about 97% reduction in thermal conductivity in the alloys with nanoscale porosity. Such an extreme reduction in thermal conductivity is due to the interplay between phonon-boundary and phonon mass mismatch scatterings. 

Bulk AlAs at 500K
<p align="center">
<img src="Bandpass/Fig-00-bulk-AlAs-500K-L-100nm.png" align="center" alt="drawing" width="700px"> 
</p> 
Bulk AlAs with ?? = 0.25 and L = 100 nm at 500K
<p align="center">
<img src="Bandpass/Fig-01-NP-AlAs-500K-L-100nm-025.png" align="center" alt="drawing" width="700px"> 
</p> 
Bulk Al<sub>0.8</sub>In<sub>0.2</sub>As at 500K
<p align="center">
<img src="Bandpass/Fig-02-bulk-Al08In02As-500K-L-100nm.png" align="center" alt="drawing" width="700px"> 
</p> 
Bulk Al<sub>0.8</sub>In<sub>0.2</sub>As with ?? = 0.25 and L = 100 nm at 500K
<p align="center">
<img src="Bandpass/Fig-03-NP-Al08In02As-500K-L-100nm-025.png" align="center" alt="drawing" width="700px"> 
</p> 

# Characteristic MFP of Alloys

The characteristic MFP and bulk thermal conductivity of wide sweep of IV and III-V dielectrics at different temperatures.

AlGaAs alloys
<p align="center">
<img src="Characteristic-MFP/AlGaAs.png" align="center" alt="drawing" width="700px"> 
</p> 
AlGaN alloys
<p align="center">
<img src="Characteristic-MFP/AlGaN.png" align="center" alt="drawing" width="700px"> 
</p> 
AlInAs alloys
<p align="center">
<img src="Characteristic-MFP/AlInAs.png" align="center" alt="drawing" width="700px"> 
</p> 
GeSn alloys
<p align="center">
<img src="Characteristic-MFP/GeSn.png" align="center" alt="drawing" width="700px"> 
</p> 
InGaP alloys
<p align="center">
<img src="Characteristic-MFP/InGaP.png" align="center" alt="drawing" width="700px"> 
</p> 
SiGe alloys
<p align="center">
<img src="Characteristic-MFP/SiGe.png" align="center" alt="drawing" width="700px"> 
</p> 
SiSn alloys
<p align="center">
<img src="Characteristic-MFP/SiSn.png" align="center" alt="drawing" width="700px"> 
</p> 

# Lattice Thermal Conductivity

The lattice thermal conductvity and phonon scattering in Group III-V 

<p align="center">
<img src="Bulk-Thermal-Conductivity/Picture1.png" align="center" alt="drawing" width="1100px"> 
</p> 

The lattice thermal conductvity and phonon scattering in Group-IV 

<p align="center">
<img src="Bulk-Thermal-Conductivity/Picture2.png" align="center" alt="drawing" width="700px"> 
</p> 

# Tables of the Lattice Thermal Conductivity Charractristic MFP in Dielectrics and Diffusive Suppression for Pores with Different Shapes and Porosity

<p align="center">
<img src="Table.png" align="center" alt="drawing" width="700px"> 
</p> 

