# Challenge 5: Metadata Analysis (exiftool)

The objective was to analyze the provided **MP4 video file**, `Cult Video.mp4`, to locate and extract a flag hidden within its file structure.

## Tools Used
* **exiftool:** Utilized for comprehensive extraction of metadata from the video file.
* **steghide:** Attempted for steganography detection (unsuccessful).

## Methodology and Analysis

### 1. Initial Attempt and Pivoting
I first attempted to use the `steghide info` command, based on its success in a previous challenge. However, the tool correctly reported that the `.mp4` file format was not supported for steganography. Recognizing that **metadata** is a common hiding spot for flags in media files, I immediately pivoted to using `exiftool`.

### 2. Metadata Extraction

I ran the `exiftool` command against the video file:

```bash
exiftool "Cult Video.mp4"
```
### 3. Key Finding and Extraction
I examined the extensive output, which detailed the video's creation and format. I specifically focused on common hidden fields such as Title, Artist, and Comment. The flag was successfully found embedded within the Comment tag in the file's metadata:

Comment: flame{happy_halloween}
