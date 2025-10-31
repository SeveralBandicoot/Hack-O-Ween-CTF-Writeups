# Challenge 2: Linux Terminal Binary Execution

The goal for this challenge was to analyze the provided executable file, `LinkedRooms.exe`, to extract the hidden flag without needing to execute or reverse-engineer the application fully.

## Tools Used
* **Linux Command Line Interface (CLI):** Used to interact with and analyze the binary file.
* **strings command:** Used to extract all printable text sequences from the binary file.

## Thinking Process

1.  **Static Analysis Decision:** Given the file was an executable (`.exe`) and the challenge was focused on terminal execution, the most effective first step was to perform **static analysis** to check if the flag was stored in plain text within the binary itself.

2.  **Executing the strings command:** I navigated to the directory containing `LinkedRooms.exe` and executed the `strings` command:

```Bash
strings LinkedRooms.exe
```
I analyzed the extensive output, specifically searching for common CTF patterns such as flag, flame, or any other strings related to the challenge theme. The sequence skin_stealer was successfully identified within the output, which, when combined with the required flag format, yielded the final answer.

Flag: `flame{skin_stealer}`
