# CosmoLattice-DW-ETC

This repository contains extensions to the CosmoLattice framework developed during the PhD research of Aäron Rase (Vrije Universiteit Brussel), used in <a href=https://arxiv.org/pdf/2511.16649 target="_blank" rel="noopener noreferrer" > arXiv:2511.16649</a>.

The software extends CosmoLattice with functionality for

- cosmological domain wall simulations;
- Equal-Time Correlator (ETC) calculations;
- additional measurement routines;
- additional field initialisation routines.

---

## Repository structure

```
.
├── src/                 Source code
├── dependencies/        Scripts to install external libraries
├── build/               Local build directory (not version controlled)
├── CMakeLists.txt
├── LICENSE.md
└── README.md
```

---

## Requirements

The software requires

- CMake
- MPI
- FFTW
- PFFT

Installation scripts for several external libraries are provided in

```
dependencies/
```

---

## Usage Instructions

### White Noise Initial Conditions

To initialize the scalar field fluctuations using white noise, enable the white noise option in the input file.

Set:

```ini
Pbool = true
```

When `Pbool` is enabled, also define:

```ini
Pconst = <value>
```

where `Pconst` represents the square root of the variance of the initial scalar fluctuations.

---

### Calculating the area parameter (`Xi`)

The area parameter `Xi` can be calculated during the simulation by configuring the following parameters in the input file.

First, set the output frequency:

```ini
tOutputXiFreq = <time step>
```

This determines the simulation time interval at which `Xi` is calculated.

Next, select the method(s) used for calculating `Xi`:

```ini
ximethod = <method>
```

The available methods are:

| Value | Method | Description |
|---|---|---|
| `1` | Energy density method | Calculates `Xi` using the energy density of the domain walls. |
| `2` | Area method | Calculates `Xi` using the area estimator. |
| `3` | Line-of-sight method | Calculates `Xi` using the line-of-sight estimator. |

Multiple methods can be combined by concatenating their values. For example:

```ini
ximethod = 12
```

calculates `Xi` using methods 1 and 2.

```ini
ximethod = 123
```

calculates `Xi` using all three available methods.

Other valid combinations include:

```ini
ximethod = 13
ximethod = 23
ximethod = 123
```

---

### Calculating the Equal-Time Correlator (ETC)

To calculate the ETC, enable the ETC option in the input file:

```ini
WithETC = true
```

The time steps at which the ETC is calculated are controlled by:

```ini
tOutputInfreq = <time step>
```

This parameter determines the frequency of ETC output during the simulation.

---
## Running a simulation

An example parameter file is provided:

```
src/models/parameter-files/DW.in
```

Run the executable according to the standard CosmoLattice workflow.

---

## Scientific background

The extensions to the CosmoLattice framework were developed during the PhD research of

**Aäron Rase**

Vrije Universiteit Brussel (VUB)

for numerical studies of cosmological domain walls and Equal-Time Correlators.

---

## Citation

If you use this software in scientific work, please cite:

- the original CosmoLattice publication: <a href=https://arxiv.org/pdf/2102.01031.pdf target="_blank" rel="noopener noreferrer" > arXiv:2102.01031</a> and <a href=https://arxiv.org/pdf/2006.15122.pdf target="_blank" rel="noopener noreferrer" > arXiv:2006.15122</a>;
- the associated publication based on this repository (<a href=https://arxiv.org/pdf/2511.16649 target="_blank" rel="noopener noreferrer" > arXiv:2511.16649</a>);

---

## Acknowledgements

This repository is based on the original **CosmoLattice** framework developed by

- Daniel G. Figueroa
- Adrien Florio
- Francisco Torrenti
- Wessel Valkenburg

and distributed under the MIT License.

The original copyright and license have been preserved.

---

## License

This project is distributed under the MIT License.
See `LICENSE.md` for details.
