# Polynomial Commitments & Verifiable Delegation

**A Comparative Study of KZG and Benabbas–Gennaro–Vahlis (BGV) Protocols**

An academic research project completed for **CSC 73010: Modern Cryptography** at the City University of New York (CUNY), May 2025.

This repository contains my **research report and class presentation** comparing two approaches to verifying computations performed by untrusted parties:

1. **KZG polynomial commitments** — introduced by Kate, Zaverucha, and Goldberg.
2. **Verifiable delegation of computation** — developed by Benabbas, Gennaro, and Vahlis.

> **Project scope:** This is a literature-based technical analysis and presentation, **not** a software implementation, cryptographic library, experimental benchmark, or independent security proof.

## Research question

How can a resource-constrained client efficiently verify results produced by an untrusted server without repeating the computation itself?

Both approaches use algebraic techniques to provide compact evidence of correctness, but differ in the security model, cryptographic assumptions, setup requirements, and verification audience.

## My contributions

For this course project, I:

- Studied the original KZG and Benabbas–Gennaro–Vahlis research papers and relevant cryptographic foundations.
- Explained polynomial commitments, evaluation witnesses, bilinear pairings, algebraic pseudorandom functions (PRFs), and closed-form efficiency.
- Compared the schemes' hardness assumptions, including discrete logarithm (DL), decisional Diffie–Hellman (DDH), strong Diffie–Hellman (SDH) variants, and subgroup-membership assumptions in relevant extensions.
- Analyzed proof size, verifier/prover costs, structured-reference-string requirements, public versus private verification, and the implications for large datasets.
- Examined application areas such as verifiable secret sharing, zero-knowledge sets, selective-disclosure credentials, proofs of retrievability, keyword search, and verifiable databases.
- Authored a technical report and prepared a presentation communicating the comparison and its trade-offs.

## Deliverables

| Deliverable | Description |
| --- | --- |
| [Research report](report/CryptoFinal.pdf) | 12-page comparative analysis of assumptions, constructions, applications, security, and efficiency. |
| [Class presentation](presentation/CryptoFinalPresentation.pdf) | 12-slide overview of the motivation, schemes, comparisons, and applications. |

The links above work once the two original PDFs are placed in the indicated repository folders.

## Comparison at a glance

| Dimension | KZG polynomial commitments | BGV verifiable delegation |
| --- | --- | --- |
| Core goal | Commit to a polynomial and prove claimed evaluations | Verify outsourced computations over large datasets |
| Evidence | Compact evaluation witness | Authentication/proof for a delegated result |
| Verification | Publicly verifiable | Typically verified by the client holding a secret key |
| Setup | Structured reference string (SRS) | No KZG-style structured reference string for the basic construction |
| Assumptions explored | DL, t-SDH, and related assumptions for batch openings | DDH, stronger variants for faster verification, and subgroup membership for database extensions |
| Strength emphasized in the report | Succinct, publicly checkable polynomial openings | Efficient repeated verification for resource-constrained clients |

These are high-level comparisons of the **particular constructions reviewed**, not universal properties of all polynomial-commitment or verifiable-computation protocols.

## Topics covered

### 1. Cryptographic foundations
Bilinear pairings, polynomial arithmetic, discrete-logarithm-type hardness assumptions, algebraic PRFs, and closed-form efficiency.

### 2. KZG polynomial commitments
Structured setup; commitment and evaluation-opening algorithms; pairing-based verification; batch opening; and public verifiability.

### 3. Benabbas–Gennaro–Vahlis delegation
Outsourcing polynomial evaluations; authentication using algebraic PRFs; efficient client verification; and extensions to keyword search, retrievability, and verifiable databases.

### 4. Security and performance trade-offs
The report compares underlying assumptions, setup costs, compact proofs, verification models, asymptotic work, and use cases.

### 5. Applications and conclusions
The project discusses where public verification and compact polynomial openings are useful versus scenarios emphasizing repeated private verification of large outsourced datasets.

## Primary research references

- **Kate, A., Zaverucha, G. M., & Goldberg, I.** *Constant-Size Commitments to Polynomials and Their Applications* (ASIACRYPT 2010). [Cryptology ePrint 2010/486](https://eprint.iacr.org/2010/486).
- **Benabbas, S., Gennaro, R., & Vahlis, Y.** *Verifiable Delegation of Computation over Large Datasets* (2011). [Cryptology ePrint 2011/132](https://eprint.iacr.org/2011/132).

The report includes its own bibliography. The links above identify the two main research papers provided with this project; they are not original work by the repository author.

## Author

**Angel Coronel**  
CSC 73010 — Modern Cryptography, CUNY  
May 2025

## Note

This repository archives coursework and summarizes published cryptographic research. It should not be interpreted as a production-ready cryptographic implementation or a claim of independently proving the security of either protocol.
