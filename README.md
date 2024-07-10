# FTIO and TMIO for Predicting the Period of I/O Phases
This repository contains [FTIO](https://github.com/tuda-parallel/FTIO) and [TMIO](https://github.com/tuda-parallel/TMIO). This repo deploys both tools using submodules. For installation instructions see [installation](#installation). The official repos of both tools are located at: 
- FTIO: https://github.com/tuda-parallel/FTIO
- TMIO: https://github.com/tuda-parallel/TMIO

To create Extra-P models using the extension developed in the ADMIRE project, see [Extra-P in ADMIRE](#extra-p-in-admire).

## Table of Content
- [FTIO and TMIO for Predicting the Period of I/O Phases](#ftio-and-tmio-for-predicting-the-period-of-io-phases)
	- [Table of Content](#table-of-content)
	- [Overview of the Tools in this Repo](#overview-of-the-tools-in-this-repo)
		- [FTIO](#ftio)
		- [TMIO](#tmio)
	- [Installation](#installation)
	- [Quick Start](#quick-start)
	- [Extra-P in ADMIRE](#extra-p-in-admire)
	- [Contributing](#contributing)
	- [License](#license)
	- [Contact and Authors](#contact-and-authors)
	- [Acknowledgments](#acknowledgments)
	- [Citation](#citation)
	- [Publications](#publications)

## Overview of the Tools in this Repo
Below, FTIO and TMIO are briefly described.

### FTIO
![GitHub Release](https://img.shields.io/github/v/release/tuda-parallel/FTIO)
![GitHub Release Date](https://img.shields.io/github/release-date/tuda-parallel/FTIO)
![](https://img.shields.io/github/last-commit/tuda-parallel/FTIO)
![contributors](https://img.shields.io/github/contributors/tuda-parallel/FTIO)
![issues](https://img.shields.io/github/issues/tuda-parallel/FTIO)
![](https://img.shields.io/github/languages/code-size/tuda-parallel/FTIO)
![](https://img.shields.io/github/languages/top/tuda-parallel/FTIO)
![license](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)
[![Upload Python Package](https://img.shields.io/github/actions/workflow/status/tuda-parallel/FTIO/python-publish.yml)](https://github.com/tuda-parallel/FTIO/actions/workflows/python-publish.yml)
[![Python Package](https://img.shields.io/pypi/status/ftio-hpc)](https://pypi.org/project/ftio-hpc/)


FTIO captures periodic I/O using frequency techniques.
FTIO allows [*offline* detection](https://github.com/tuda-parallel/FTIO/tree/main/docs/approach.md#offline-detection) and [*online* prediction](https://github.com/tuda-parallel/FTIO/tree/main/docs/approach.md#online-prediction) of periodic I/O phases.
FTIO uses the discrete Fourier transform (DFT), combined with outlier detection methods to extract the dominant frequency in the signal.
Additional metrics gauge the confidence in the output and tell how far from being periodic the signal is.
A complete description of the approach is provided [here](https://github.com/tuda-parallel/FTIO/tree/main/docs/approach.md).

### TMIO
![GitHub Release](https://img.shields.io/github/v/release/tuda-parallel/TMIO)
![GitHub Release](https://img.shields.io/github/release-date/tuda-parallel/TMIO)
![](https://img.shields.io/github/last-commit/tuda-parallel/TMIO)
![contributors](https://img.shields.io/github/contributors/tuda-parallel/TMIO)
![issues](https://img.shields.io/github/issues/tuda-parallel/TMIO)
![](https://img.shields.io/github/languages/code-size/tuda-parallel/TMIO)
![](https://img.shields.io/github/languages/top/tuda-parallel/TMIO)
![license](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)

TMIO is a C++ tracing library that can be easily
attached to existing code to monitor MPI-IO online. The tool traces synchronous as well as asynchronous I/O.
TMIO offers a C as well as a C++ interface.
We provide two methods for linking the library to the application, depending on whether the information is used for [offline](https://github.com/tuda-parallel/TMIO/?tab=readme-ov-file#offline-analysis) or [online](https://github.com/tuda-parallel/TMIO/?tab=readme-ov-file#online-analysis) analysis.
The obtained traces can be analyzed as explained here [exploring the traces](https://github.com/tuda-parallel/TMIO/?tab=readme-ov-file#exploring-the-traces).


<br><br>

## Installation 
To install both tools either head to  [FTIO](https://github.com/tuda-parallel/FTIO) and [TMIO](https://github.com/tuda-parallel/TMIO) and install them as described in their Readme, or simply execute:

``` sh
git clone git@github.com:admire-eurohpc/IO_phase_prediction.git
cd IO_phase_prediction

# option 1
git pull --recurse-submodules

# option 2
git pull
git submodule init
git submodule update

# Keep your modules up to date to the latest
# releases by calling: 
git submodule update --recursive --remote

```

<br><br>

## Quick Start
For usage of the tools see:
- [FTIO usage instructions](https://github.com/tuda-parallel/FTIO?tab=readme-ov-file#usage).
- [TMIO usage instructions](https://github.com/tuda-parallel/TMIO/?tab=readme-ov-file#usage)

<br><br>


## Extra-P in ADMIRE
During the project, [Extra-P](https://github.com/extra-p/extrap) has been extended to model I/O. This is documented [here](https://github.com/extra-p/extrap/blob/master/docs/modeling-io-performance.md). Furthermore, the metric proxy ([official GitHub](https://github.com/besnardjb/proxy_v2) or [ADMIRE GitHub](https://github.com/admire-eurohpc/metric_proxy)) internally calls Extra-P to generate performance models from the captured Profiles. For that, simply go to `http://localhost:1337/model.html` after running the proxy as described [here](https://github.com/besnardjb/proxy_v2). For more info, run the proxy and see `http://localhost:1337/doc.html`.

<br><br>

## Contributing

If you have a suggestion that would make this better, please fork the repository and create a pull request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

<br><br>

## License

![license]( https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)

Distributed under the BSD 3-Clause License. See [LISCENCE](./LICENSE) for more information.

<br><br>

## Contact and Authors

[![][parallel.bedge]][parallel_website]

- Ahmad Tarraf: <ahmad.tarraf@tu-darmstadt.de>

<br><br>

## Acknowledgments

This work is a result of cooperation between the Technical University of Darmstadt and INRIA in scope of the [EuroHPC ADMIRE project](https://admire-eurohpc.eu/).


<br><br>

## Citation

```
 @inproceedings{Tarraf_Bandet_Boito_Pallez_Wolf_2024, 
  author={Tarraf, Ahmad and Bandet, Alexis and Boito, Francieli and Pallez, Guillaume and Wolf, Felix},
  title={Capturing Periodic I/O Using Frequency Techniques}, 
  booktitle={2024 IEEE International Parallel and Distributed Processing Symposium (IPDPS)}, 
  address={San Francisco, CA, USA}, 
  year={2024},
  month=may, 
  pages={1–14}, 
  notes = {(accepted)}
 }
```

<br><br>

## Publications

1. A. Tarraf, A. Bandet, F. Boito, G. Pallez, and F. Wolf, “Capturing Periodic I/O Using Frequency Techniques,” in 2024 IEEE International Parallel and Distributed Processing Symposium (IPDPS), San Francisco, CA, USA, May 2024, pp. 1–14.



[parallel_website]: https://www.parallel.informatik.tu-darmstadt.de/laboratory/team/tarraf/tarraf.html
[parallel.bedge]: https://img.shields.io/badge/Parallel_Programming:-Ahmad_Tarraf-blue
