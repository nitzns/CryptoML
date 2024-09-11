# CryptoML: Machine Learning Insights into Ciphertext and Encryption Schemas

## Introduction
In recent years, machine learning (ML) has made significant strides, enabling increasingly complex tasks to be performed using learning algorithms. A learning algorithm is defined by its ability to improve performance on a given task T, measured by a performance metric P, based on experience E (Tom Mitchell, 1998).

This project explores the intersection of ML and cryptography, aiming to investigate whether a learning algorithm can leak information about ciphertexts. Specifically, the project attempts to:

Detect the encryption schema used.
Identify the type of original plaintext (e.g., binary file, English text).
The study tests both classic encryption methods like the Caesar cipher and XOR, as well as modern encryption techniques such as AES, DES, and 3-DES.

## Libraries Used

numpy: For mathematical operations.
pycryptodome: An implementation of modern ciphers in Python.
tensorflow: Core ML framework used for building models.
keras: High-level API built on top of TensorFlow for ease in creating, training, and testing models.
termplot: Library for plotting charts in the terminal.

## Trials and Results
Each trial was conducted to minimize loss (close to 0) and maximize accuracy (close to 1). The ML models were trained using online data generation to avoid overfitting.

Trial #1: Sanity Test
Goal: Classify between unencrypted English text and binary data.
Model: FC Neural Network, 1 hidden layer.
Result: Success.

Trial #2: Detect Plaintext Type from SHIFT Encrypted Ciphertext
Goal: Recognize the type of plaintext (English or binary) from ciphertext encrypted with the SHIFT cipher.
Model: FC Neural Network, 1 hidden layer.
Result: Success.

Trial #3: Detect Plaintext Type from XOR Encrypted Ciphertext
Goal: Detect plaintext type from XOR-encrypted ciphertext.
Model: FC Neural Network, 1 hidden layer.
Result: Success.

Trial #4: Detect Plaintext Type from OTP Encrypted Ciphertext
Goal: Attempt to detect plaintext type from ciphertext encrypted with a random key using a one-time pad (OTP).
Model: FC Neural Network, 1 hidden layer.
Result: Failure (as expected due to the nature of OTP encryption).

Trial #5: Detect Cipher Type (XOR or SHIFT)
Goal: Identify whether XOR or SHIFT encryption was used.
Model: FC Neural Network, 5 hidden layers, 100 units per layer.
Result: Success.

Trial #6: Detect Plaintext Type from AES Encrypted Ciphertext
Goal: Detect plaintext type from AES-encrypted ciphertext with a single key.
Model: FC Neural Network, 5 hidden layers, 100 units per layer.
Result: Failure.

Trial #7: Detect Plaintext Type from DES Encrypted Ciphertext
Goal: Detect plaintext type from DES-encrypted ciphertext.
Model: FC Neural Network, 5 hidden layers, 100 units per layer.
Result: Failure.

Trial #8: Detect Cipher Type (AES or DES)
Goal: Identify whether AES or DES encryption was used.
Model: FC Neural Network, 5 hidden layers, 100 units per layer.
Result: Partial Success (accuracy > 80%).

Trial #9: Detect Cipher Type with Random Keys (AES or DES)
Goal: Identify AES or DES encryption with randomly changing keys for each input.
Model: FC Neural Network, 5 hidden layers, 100 units per layer.
Result: Failure.

Trial #10: Detect Plaintext Type with Random Keys in SHIFT Encryption
Goal: Identify plaintext type from ciphertext using random small keys in SHIFT encryption.
Model: FC Neural Network, 5 hidden layers, 100 units per layer.
Result: Success.

Trial #11: Performance of RNN on SHIFT Cipher with Variable Input Sizes
Goal: Test the performance of RNN on SHIFT-encrypted ciphertext with varying input sizes.
Model: RNN with Conv1D → LSTM → FC architecture and dropout.
Result: Success.
