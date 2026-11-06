# Entanglement-Based BBM92 Quantum Key Distribution: Comparative Analysis of Eavesdropping Attacks

### Investigating PCCM, Quantum Circuit Learning (QCL), and Quantum-Based Attack Circuit (Q-BAC)

## Overview

This project investigates eavesdropping attacks in **BBM92 (Bennett–Brassard–Mermin–1992)**, an entanglement-based Quantum Key Distribution (QKD) protocol.

The primary objective is to implement and compare three different attack models: **PCCM, Quantum Circuit Learning (QCL), and Quantum-Based Attack Circuit (Q-BAC)**.

The simulation uses entangled quantum states and two measurement bases (Z and X) to study the interaction between legitimate users, Alice and Bob, and an eavesdropper, Eve.

A key focus is investigating whether a learnable quantum attack circuit can approach or outperform the theoretical PCCM benchmark under ideal, noise-free conditions.

## Key Features

- **BBM92 Protocol Simulation:** Implements entanglement-based quantum key distribution using Bell states.
- **Quantum Entanglement:** Uses the Bell state to establish correlations between Alice's and Bob's quantum measurements.
- **Multiple Attack Models:** Implements and compares PCCM, QCL, and Q-BAC.
- **Two-Ancilla Attack Architecture:** Models Eve's interaction with both Alice's and Bob's quantum channels using two ancilla qubits.
- **Quantum Circuit Learning:** Uses numerical optimization to investigate the performance of learnable quantum attack circuits.
- **Fidelity-Based Evaluation:** Measures Alice–Bob and Alice–Eve fidelities to analyze information preservation and eavesdropping performance.
- **Benchmark Comparison:** Evaluates learned attack circuits against the theoretical PCCM benchmark.

## BBM92 Protocol

BBM92 is an entanglement-based QKD protocol in which Alice and Bob receive correlated quantum particles from an entangled pair.

The simulation uses the Bell state:

[
|\Phi^+\rangle =
\frac{|00\rangle+|11\rangle}{\sqrt{2}}
]

Alice and Bob independently measure their respective qubits using two measurement bases:

- **Z-basis:** Computational basis ((|0\rangle, |1\rangle)).
- **X-basis:** Hadamard basis ((|+\rangle, |-\rangle)).

After measurement, Alice and Bob compare their measurement bases through a public classical channel and retain the results obtained using matching bases.

The resulting correlated measurement outcomes form the basis of the shared raw key.

## Eavesdropping Attack Models

The project investigates three attack approaches.

### 1. PCCM

PCCM serves as the theoretical benchmark for evaluating eavesdropping performance.

It provides a reference against which the learnable quantum attack models can be compared.

### 2. Quantum Circuit Learning (QCL)

QCL uses a parameterized quantum circuit whose trainable parameters are optimized numerically.

The objective is to investigate how a learnable quantum circuit can manipulate quantum correlations and improve Eve's information extraction while evaluating its effect on Bob's state.

### 3. Quantum-Based Attack Circuit (Q-BAC)

Q-BAC is the proposed quantum attack architecture investigated in this project.

It uses two ancilla qubits to model Eve's interaction with both Alice's and Bob's quantum channels.

This architecture allows the simulation to investigate Eve's access to both sides of the entangled quantum system rather than considering only a single-channel interaction.

The performance of Q-BAC is evaluated against QCL and the theoretical PCCM benchmark.

## Quantum System Architecture

The simulation models an entangled quantum communication system involving:

- **Alice:** The legitimate sender.
- **Bob:** The legitimate receiver.
- **Eve:** The potential eavesdropper.
- **Two Ancilla Qubits:** Additional quantum registers used by Eve to interact with the communication system.

The quantum system incorporates the entangled Alice–Bob state and Eve's ancilla registers.

The attack models investigate how Eve's interaction affects the quantum states and the information available to both legitimate users and the eavesdropper.

## Evaluation Metrics

The project uses quantum fidelity to evaluate the performance of different attack models.

### Alice–Bob Fidelity (F_AB)

Measures how closely Bob's quantum state matches Alice's intended quantum state.

A higher (F\_{AB}) indicates better preservation of the legitimate communication state.

### Alice–Eve Fidelity (F_AE)

Measures how closely Eve's reduced quantum state matches Alice's reference state.

A higher (F\_{AE}) indicates that Eve has obtained a quantum state with greater similarity to Alice's reference state.

Both metrics are used together to investigate the trade-off between legitimate communication quality and eavesdropping performance.

## Numerical Optimization

The project evaluates the attack models across **10 target fidelity values** using numerical optimization.

The optimization process involves:

1. Constructing the quantum states and attack circuits.
2. Applying Eve's interaction with the entangled communication system.
3. Calculating the resulting quantum states.
4. Evaluating Alice–Bob and Alice–Eve fidelities.
5. Using numerical optimization to investigate the attack circuit parameters.
6. Comparing the resulting fidelity values across different attack models.

This process allows the project to examine how changes in the target fidelity affect the performance of the different eavesdropping strategies.

## Experimental Scope

The initial experiments focus on ideal, noise-free quantum simulations.

The primary comparisons include:

- PCCM versus QCL.
- PCCM versus Q-BAC.
- QCL versus Q-BAC.
- Alice–Bob fidelity across different target fidelity values.
- Alice–Eve fidelity across different target fidelity values.

The central research question is whether a learnable quantum attack architecture, particularly Q-BAC, can achieve competitive eavesdropping performance compared with the theoretical PCCM benchmark.

## Technologies Used

- **Python** – Main programming language.
- **JAX** – Numerical computation and optimization.
- **NumPy** – Quantum state and matrix operations.
- **SciPy** – Numerical optimization.
- **Pandas** – Experimental data organization and analysis.

## Research Objective

The central objective of this project is to investigate learnable quantum eavesdropping strategies in entanglement-based Quantum Key Distribution.

By comparing PCCM, QCL, and Q-BAC under a common BBM92 simulation framework, the project explores whether quantum circuit learning and interactions with both sides of an entangled communication system can provide advantages in Eve's information extraction.

The comparison with PCCM provides a theoretical reference for evaluating the effectiveness of the proposed Q-BAC architecture.

---

**Project Focus:** Quantum Key Distribution | BBM92 | Quantum Cryptography | Quantum Circuit Learning | Quantum Eavesdropping | Quantum Entanglement | Quantum Fidelity
