# Entanglement-Based BBM92 Quantum Key Distribution: Comparative Analysis of Eavesdropping Attacks

**Investigating PCCM, Quantum Circuit Learning (QCL), and Quantum-Based Attack Circuit (Q-BAC)**

## Overview

This project investigates quantum eavesdropping attacks in **BBM92 (Bennett–Brassard–Mermin–1992)**, an entanglement-based Quantum Key Distribution (QKD) protocol.

The project implements and compares three attack models:

- **PCCM** – Theoretical benchmark.
- **QCL (Quantum Circuit Learning)** – A learnable quantum attack model.
- **Q-BAC (Quantum-Based Attack Circuit)** – The proposed quantum attack architecture.

Using an entangled quantum system, the simulation studies how Eve's interaction with the communication channels affects the quantum states of Alice and Bob and the information accessible to Eve.

The main research objective is to investigate whether a learnable quantum attack architecture can achieve competitive performance compared with the theoretical PCCM benchmark under ideal, noise-free conditions.

## Key Features

- **BBM92 Simulation:** Models entanglement-based quantum communication using Bell states.
- **Quantum Entanglement:** Uses correlated quantum states to represent Alice and Bob's shared quantum system.
- **Multiple Attack Models:** Implements and compares PCCM, QCL, and Q-BAC.
- **Two-Ancilla Architecture:** Models Eve's interaction with both Alice's and Bob's quantum channels using two ancilla qubits.
- **Quantum Circuit Learning:** Applies numerical optimization to investigate learnable attack circuits.
- **Fidelity Evaluation:** Measures Alice–Bob and Alice–Eve fidelities.
- **Benchmark Comparison:** Evaluates QCL and Q-BAC against the PCCM theoretical benchmark.

## BBM92 Protocol

BBM92 is an entanglement-based QKD protocol in which Alice and Bob share quantum particles generated as an entangled pair.

The simulation uses the Bell state:

$$
|\Phi^+\rangle = \frac{|00\rangle+|11\rangle}{\sqrt{2}}
$$

Alice and Bob independently measure their respective qubits using two measurement bases:

| Measurement Basis | Quantum States |
|---|---|
| Z-basis | $|0\rangle,\ |1\rangle$ |
| X-basis | $|+\rangle,\ |-\rangle$ |

After measurement, Alice and Bob compare their measurement bases through a public classical channel. They retain the results obtained using matching bases.

These correlated measurement outcomes form the basis of their shared raw key.

## Eavesdropping Attack Models

### 1. PCCM

PCCM serves as the theoretical benchmark for evaluating eavesdropping performance. It provides a reference for comparing the learnable quantum attack models.

### 2. Quantum Circuit Learning (QCL)

QCL uses a parameterized quantum circuit with trainable parameters.

Numerical optimization updates these parameters to investigate how a learnable quantum circuit can affect the quantum states of Bob and Eve and improve Eve's information extraction.

### 3. Quantum-Based Attack Circuit (Q-BAC)

Q-BAC is the proposed quantum attack architecture investigated in this project.

It uses **two ancilla qubits** to model Eve's interaction with both Alice's and Bob's quantum channels.

This architecture allows the simulation to investigate Eve's interaction with both sides of the entangled quantum system rather than considering only a single-channel interaction.

Q-BAC is evaluated against QCL and the theoretical PCCM benchmark.

## Quantum System Architecture

The simulation represents an entangled quantum communication system involving:

| Component | Description |
|---|---|
| Alice | Legitimate sender |
| Bob | Legitimate receiver |
| Eve | Potential eavesdropper |
| Ancilla Qubit 1 | Additional quantum register used by Eve |
| Ancilla Qubit 2 | Additional quantum register used by Eve |

The system combines the entangled Alice–Bob state with Eve's two ancilla qubits. The attack models investigate how Eve's interactions affect the quantum states and the information available to the legitimate users and the eavesdropper.

## Evaluation Metrics

The attack models are evaluated using quantum fidelity.

### Alice–Bob Fidelity ($F_{AB}$)

Measures how closely Bob's quantum state matches Alice's reference state.

A higher $F_{AB}$ indicates better preservation of the legitimate communication state.

### Alice–Eve Fidelity ($F_{AE}$)

Measures how closely Eve's reduced quantum state matches Alice's reference state.

A higher $F_{AE}$ indicates greater similarity between Eve's state and Alice's reference state.

Both metrics are analyzed together to study the trade-off between legitimate communication quality and eavesdropping performance.

## Numerical Optimization

The project evaluates the attack models across **10 target fidelity values** using numerical optimization.

The evaluation process involves:

1. Constructing the quantum states and attack circuits.
2. Applying Eve's interaction with the entangled communication system.
3. Calculating the resulting quantum states.
4. Evaluating Alice–Bob and Alice–Eve fidelities.
5. Optimizing the attack circuit parameters.
6. Comparing the resulting fidelity values across different attack models.

This allows the project to investigate how different target fidelity values affect the performance of the eavesdropping strategies.

## Experimental Scope

The initial experiments focus on **ideal, noise-free quantum simulations**.

The main comparisons include:

- PCCM vs. QCL
- PCCM vs. Q-BAC
- QCL vs. Q-BAC
- Alice–Bob fidelity across different target fidelity values
- Alice–Eve fidelity across different target fidelity values

The central research question is whether a learnable quantum attack architecture, particularly Q-BAC, can achieve competitive eavesdropping performance compared with the theoretical PCCM benchmark.

## Technologies Used

- **Python** – Main programming language
- **JAX** – Numerical computation and optimization
- **NumPy** – Quantum state and matrix operations
- **SciPy** – Numerical optimization
- **Pandas** – Experimental data organization and analysis

## Research Objective

This project explores learnable quantum eavesdropping strategies in entanglement-based Quantum Key Distribution.

By implementing and comparing PCCM, QCL, and Q-BAC within a common BBM92 simulation framework, the research investigates whether quantum circuit learning and interactions with both sides of an entangled communication system can provide advantages in Eve's information extraction.

The PCCM benchmark provides a theoretical reference for evaluating the performance of the proposed Q-BAC architecture.

---

**Research Areas:** Quantum Key Distribution · BBM92 · Quantum Cryptography · Quantum Circuit Learning · Quantum Eavesdropping · Quantum Entanglement · Quantum Fidelity
