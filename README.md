# CosmoLattice-DW-ETC

This repository contains extensions to the CosmoLattice framework developed during the PhD research of Aäron Rase (Vrije Universiteit Brussel).

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

## Running a simulation

An example parameter file is provided:

```
src/models/parameter-files/DW.in
```

Run the executable according to the standard CosmoLattice workflow.

---

## Scientific background

The software was developed during the PhD research of

**Aäron Rase**

Vrije Universiteit Brussel (VUB)

for numerical studies of cosmological domain walls and Equal-Time Correlators.

---

## Citation

If you use this software in scientific work, please cite:

- the original CosmoLattice publication;
- the associated publication based on this repository (<a href=https://arxiv.org/pdf/2511.16649 target="_blank" rel="noopener noreferrer" > arXiv:2511.16649</a>);


A `CITATION.cff` file will be provided for citation metadata.

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
