# Secure_Complaint
Secure Complaint: Advanced Steganographic Techniques for Secure and Anonymous Audio-Based Complaint Submission
Overview
Secure Complaint is an innovative framework designed to ensure secure, private, and anonymous submission of complaint records using advanced audio steganography and cryptographic techniques. The system securely embeds encrypted user details into complaint audio files, thus eliminating the need for external mapping databases and reducing the risk of data breaches. The project combines AES-CBC encryption, bit-level obfuscation (via bit reversal and flipping), audio interpolation, and least significant bit (LSB) steganography to create a robust and efficient secure complaint submission method.

Features
Robust Encryption: Encrypts sensitive user details using the Advanced Encryption Standard (AES) in Cipher Block Chaining (CBC) mode with a 16-byte key and dynamic initialization vector (IV).
Enhanced Security: Applies additional obfuscation by performing bit reversal and bit flipping on the encrypted binary data.
Audio Interpolation: Doubles the sample count of complaint audio files, increasing the embedding capacity without compromising audio quality.
Imperceptible Data Embedding: Uses LSB substitution to embed obfuscated data within the audio samples while maintaining high perceptual quality.
Accurate Extraction: Ensures error-free recovery of user details with a zero Bit Error Rate (BER) across all test cases.
Quality Evaluation: Evaluates the integrity and fidelity of the stego-audio using metrics like Peak Signal-to-Noise Ratio (PSNR), Structural Similarity Index Measure (SSIM), and Bit Error Rate (BER).
Repository Details
Current Version: V1
Repository: https://github.com/amirlyphd/Secure_Complaint
License: MIT License
Programming Language: Python
Key Dependencies:
pycryptodome
SciPy
NumPy
librosa
Support Email: amirlyphd@gmail.com
Framework Phases
1. Data Encryption & Embedding Phase
Input:
User details are read from text files.
Complaint audio is loaded from .wav files.
Encryption:
User details are encrypted using AES in CBC mode.
The ciphertext is converted to binary and further obfuscated using bit reversal and flipping.
Audio Processing:
Complaint audio undergoes linear interpolation to double the sample count, creating ample capacity for data embedding.
Embedding:
The obfuscated binary data is embedded into the least significant bits (LSBs) of the interpolated audio samples.
This phase is described in detail in the paper (see the Encryption & Embedding Phase section 
).

2. Data Extraction & Decryption Phase
Extraction:
The hidden bits are extracted by retrieving the LSBs from the stego audio samples.
Deobfuscation:
The obfuscation is reversed (i.e., bit flipping and reversal) to recover the original binary data.
Decryption:
The recovered binary data is decrypted using AES-CBC to yield the original user details.
The extraction and decryption process is clearly outlined in the paper (see the Data Extraction & Decryption Phase section 
).

3. Evaluation Phase
Quality Metrics:
PSNR: Measures the fidelity of the stego-audio compared to the original audio.
SSIM: Evaluates the perceptual similarity between the two audio signals.
BER: Confirms error-free extraction of embedded data.
Performance:
Embedding and extraction are performed in milliseconds, ensuring the system’s efficiency.
The evaluation details, including numerical performance metrics and qualitative waveform/spectrogram comparisons, are provided in the paper 
.
