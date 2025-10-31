# Challenge 6: Classical Cryptography (Substitution Cipher)

The goal was to decipher an ancient, encrypted text found on a tablet using a partial translation key provided as an image.

## Tools Used
* **Image Viewer:** Used to reference the provided partial translation key.
* **Text Editor / Manual Substitution:** Employed to apply the known key and perform manual decryption.
* **Frequency Analysis:** Utilized to infer unknown characters based on common word patterns and letter frequency.

## Methodology and Analysis

### 1. Key Application and Initial Decryption

I started by applying the known letter translations provided in the accompanying image file to the encrypted text. This provided a partial decryption, revealing small fragments of clear text and establishing initial linguistic context.

### 2. Pattern Recognition and Decryption

With the known letters in place, I used principles of **frequency analysis** and **pattern recognition** (which is standard procedure for solving substitution ciphers) to infer the remaining unknown characters. This involved matching common English letters (E, T, A, O, I, N) to the most frequent unknown ciphertext characters.

### 3. Confirmation and Extraction

The complete decryption process, based on the established key, led to the discovery of a distinct, common word that filled the entire cipher text.

The full decrypted string was revealed to be **ABRACADABRA**.

## Final Flag

**Flag:** `flame{ABRACADABRA}`
