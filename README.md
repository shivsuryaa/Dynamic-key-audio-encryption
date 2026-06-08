# Secure Audio Encryption Using EMD and Chaotic Mapping with Dynamic Key Generation

## Overview

This project implements a secure audio encryption and decryption system using Empirical Mode Decomposition (EMD) and a 2D Cosine Logistic Chaotic Map. The proposed method enhances security by introducing dynamic key generation using a timestamp and random seed. The system also employs scrambling and XOR-based encryption to protect audio data from unauthorized access.

## Features

* Audio encryption and decryption
* Dynamic key generation using timestamp and random seed
* SHA3-512 based parameter generation
* 2D Cosine Logistic Map for chaotic sequence generation
* Audio sample scrambling
* EMD-based signal decomposition
* XOR encryption of the residual signal
* Reconstruction of the original audio during decryption

## Methodology

### Encryption Process

1. Load the original audio signal.
2. Generate timestamp and random seed.
3. Create SHA3-512 hash from audio data, timestamp, and seed.
4. Extract chaotic parameters from the hash.
5. Generate chaotic sequence using the 2D Cosine Logistic Map.
6. Scramble the audio signal.
7. Apply EMD decomposition to obtain IMFs and residue.
8. Encrypt the residue using XOR with the chaotic sequence.
9. Recombine IMFs and encrypted residue to produce encrypted audio.

### Decryption Process

1. Load the encrypted audio signal.
2. Use the same timestamp and random seed.
3. Regenerate the SHA3-512 hash.
4. Extract chaotic parameters.
5. Generate the same chaotic sequence.
6. Apply EMD decomposition.
7. Decrypt the residue using XOR.
8. Perform descrambling.
9. Reconstruct the original audio signal.

## Technologies Used

* Python
* NumPy
* Librosa
* PyEMD
* Matplotlib
* Hashlib

## Security Analysis

The system was evaluated using:

* Statistical Analysis
* Correlation Analysis
* Differential Attack Analysis

Results indicate improved randomness, low correlation between original and encrypted audio, and strong resistance against attacks.

## Time Complexity

| Operation                   | Complexity |
| --------------------------- | ---------- |
| SHA3-512 Key Generation     | O(N)       |
| Chaotic Sequence Generation | O(N)       |
| Scrambling                  | O(N)       |
| XOR Encryption              | O(N)       |
| EMD Decomposition           | O(N²)      |
| Overall Complexity          | O(N²)      |

## Advantages

* Strong security
* High randomness
* Dynamic key generation
* Accurate audio reconstruction
* Increased resistance to attacks

## Limitations

* EMD introduces high computational cost
* Not suitable for real-time processing
* Requires synchronization of key parameters

## Conclusion

The project successfully demonstrates a secure audio encryption system using EMD and chaotic mapping. The inclusion of timestamp-based dynamic key generation and scrambling improves security while maintaining accurate decryption and reconstruction of the original audio signal.
