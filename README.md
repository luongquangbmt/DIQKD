# DIQKD

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/wikiti/pandoc-book-template/blob/master/LICENSE.md)
https://www.overleaf.com/4644944989cysckmnyxwjr

# Architecture
core: Where the core program of OpenQSDS resides

qw_search: Where the Quantum Walk Search algorithm resides

qkd: in the future, qkd algorithm will be placed here

# Introduction
The objective of this project is to build a Quantum Computing simulator in Maxima with the following characteristics:



1. OpQSDS programming language development.
  
    1. Ability to generate general quantum circuits by specifying parameters, for example the number of qubits, a natural number, the size of a set, etc.

    2. Ability to integrate data into the quantum gates of the circuit (wire the data), with the aim of reducing the number of required qubits.

    3. Use of general quantum gates (generalized Toffoli, etc) to facilitate algorithm coding.

    4. Automatic optimization of quantum circuits.

    5. Simulation of errors during the execution of quantum algorithms.

    6. Visualization of the quantum state at intermediate points in the execution of algorithms.

    7. Use of classical calculations, for example for conditional management, during quantum computing in order to reduce the number of required qubits.

    8. The simulator will be integrated into Maxima as a library for use as free software.



2. Code generation for Qiskit and OpenQASM.

5. Implementation in OpenQSDS of error-correcting quantum codes.

4. Simulation in OpenQSDS of qubit errors.

5. Implementation in OpenQSDS of QKD protocols.
    1. Introduction 
        1.  QKD
        2.  OpenQSDS
    2. QKD Protocol (B88)
        1. Protocol Overview
        2. Open QSDS Implementation
    2. Entangled QKD Protocol (Ekert91)
        1. Protocol Overview
        2. Open QSDS Implementation
    3. DIQKD Protocol (Acin07) 
        1. Protocol Overview
        2. Open QSDS Implementation
    4. Risk & Security Analysis
        1. Noise Simulation
        2. Analysis

6. Design of quantum codes that correct errors in two qubits.
