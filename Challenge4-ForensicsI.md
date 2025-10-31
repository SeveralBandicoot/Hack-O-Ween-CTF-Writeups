# Challenge 4: Steganography, Decryption, and Manual Decoding

The goal of this multi-step challenge was to analyze an intercepted audio transmission, `Intercepted_Transmission.wav`, determine if data was embedded within it, and then extract the final flag. This challenge combined steganography, encryption, and manual decoding.

## Tools Used
* **steghide:** Used for static analysis to detect and identify hidden data embedded within the `.wav` carrier file.
* **Online Morse Code Translator:** Utilized to decode the manually extracted audio-based message.
* **exiftool:** Considered for metadata extraction, though not ultimately necessary for the final flag.

## Methodology and Thought Process

### 1. Initial Analysis and Steganography Detection

The initial listening of the `Intercepted_Transmission.wav` file yielded no discernible speech, suggesting the file's primary purpose was to act as a **carrier for hidden data**.

I used `steghide` to analyze the file for hidden data, which is standard practice for audio steganography analysis:

```bash
steghide info Intercepted_Transmission.wav
```
By accepting the prompt to check for embedded data and submitting a blank passphrase (by pressing enter), the output provided crucial information:

Embedded file: "morse.wav"

Encryption: rijndael-128, cbc (a form of AES)

This confirmed that a second file (morse.wav) was hidden inside the transmission file and was encrypted.

2. Manual Decoding of the Passphrase
Attempting to extract the morse.wav file directly using steghide failed, as the encryption required an unknown passphrase. This prompted a change in strategy: the encrypted file's content must be the passphrase itself, or a clue leading to it.

I then listened to the morse.wav file and confirmed it contained only Morse code audio signals.

Since tool-based extraction was blocked, I pivoted to manual decoding using an online audio Morse code translator. This successfully translated the auditory message to the string: "H3LP=US".

3. Flag Extraction
The decoded message, "H3LP=US", was determined to be the final flag's value, which, when combined with the required flag format, successfully solved the challenge.

This challenge was valuable as it demonstrated the complexity of multi-layered security concepts, requiring persistence and strategic pivoting when one method (tool-based extraction) was blocked by an encryption layer.

Result
The message hidden in the audio file was successfully decoded to reveal the final flag.

Flag: flame{H3LP=US}
