# Ex. No. 8 — Use StegExpose to Detect Hidden Data in Images

## Digital Forensics Lab

### Aim / Description

**StegExpose** is a tool used to detect possible hidden data in images using steganography analysis.

It works by evaluating the statistical properties of an image and producing a **suspect score** to estimate whether hidden data may be embedded in the image.

This experiment demonstrates how to install and run StegExpose, analyze individual images, perform batch analysis, and interpret the resulting suspect score.

---

# Prerequisites

The following are required:

* Java Runtime Environment (JRE)
* StegExpose
* Test images
* Command Prompt / Terminal

StegExpose is Java-based, so Java must be installed before running the tool.

---

# 1. Download and Set Up StegExpose

## 1.1 Download StegExpose

Download the **StegExpose `.jar` file** from the official GitHub repository.

The required file is:

```text
StegExpose.jar
```

---

## 1.2 Install Java

Install the Java Runtime Environment if Java is not already installed.

Verify Java installation using:

```bash
java -version
```

If Java is installed correctly, the installed Java version will be displayed.

---

## 1.3 Prepare the Working Directory

Create a folder for the experiment.

Example:

```text
StegExpose-Lab/
│
├── StegExpose.jar
├── test_image.png
└── results/
```

Place the downloaded `StegExpose.jar` file inside the working directory.

The original experiment specifies placing the `.jar` file in a folder where the image files will be analyzed.

---

# 2. Select Images for Analysis

Collect the images that need to be examined for possible hidden data.

StegExpose supports common image formats such as:

```text
.png
.jpg
.jpeg
.bmp
```

Example:

```text
images/
├── clean_image.png
├── test_image.jpg
└── suspect_image.bmp
```

The original experiment identifies PNG, JPG, and BMP as supported example image formats.

---

# 3. Open Command Prompt or Terminal

Open:

**Windows:**

```text
Command Prompt
```

or

**Linux/macOS:**

```text
Terminal
```

Navigate to the folder containing `StegExpose.jar`.

For Windows:

```bash
cd C:\StegExpose-Lab
```

For Linux/macOS:

```bash
cd ~/StegExpose-Lab
```

The lab procedure requires navigating to the directory containing the StegExpose JAR file before executing the commands.

---

# 4. Analyze a Single Image

Use the following command:

```bash
java -jar StegExpose.jar <image_file_path>
```

Example:

```bash
java -jar StegExpose.jar test_image.png
```

Replace:

```text
<image_file_path>
```

with the actual path of the image.

For example:

```bash
java -jar StegExpose.jar C:\StegExpose-Lab\images\suspect_image.png
```

The original experiment specifies this command for analyzing an individual image.

---

# 5. Analyze the Output

After the image has been analyzed, StegExpose provides a **suspect score**.

The score ranges between:

```text
0 and 1
```

A higher score indicates a greater likelihood that hidden data may be present according to the experiment's stated thresholds.

---

## Suspect Score Interpretation

|           Score | Interpretation               |
| --------------: | ---------------------------- |
| Less than `0.2` | Image is considered clean    |
|     `0.2 – 0.3` | Possible hidden data         |
|     Above `0.3` | Steganography likely present |

These threshold interpretations are the ones specified in the uploaded experiment.

> **Note:** A StegExpose score is a detection indicator, not proof by itself that an image contains hidden data. Further forensic examination may be required.

---

# 6. Example Output

Run:

```bash
java -jar StegExpose.jar suspect_image.png
```

Example output:

```text
Analyzing suspect_image.png...
Result: 0.4
Steganography likely present
```

The uploaded experiment provides this example output with a suspect score of `0.4`.

---

# 7. Batch Analysis

StegExpose can also analyze multiple images by specifying a folder.

Use:

```bash
java -jar StegExpose.jar <folder_path>
```

Example:

```bash
java -jar StegExpose.jar images
```

Or with an absolute path:

```bash
java -jar StegExpose.jar C:\StegExpose-Lab\images
```

Replace:

```text
<folder_path>
```

with the path containing the images to be analyzed.

The experiment specifies folder-based analysis for examining multiple images.

---

# 8. Advanced Options

StegExpose provides additional command-line options.

To view the available options, run:

```bash
java -jar StegExpose.jar --help
```

This can be used to examine available parameters such as sensitivity and output verbosity.

---

# 9. Review the Results

After analysis, review the score produced for each image.

Example:

```bash
java -jar StegExpose.jar suspect_image.png
```

Example result:

```text
Analyzing suspect_image.png...
Result: 0.4
Steganography likely present
```

Record the results for each analyzed image.

A simple result table can be maintained:

| Image               | Suspect Score | Interpretation                      |
| ------------------- | ------------: | ----------------------------------- |
| `clean_image.png`   |        `0.12` | Clean according to stated threshold |
| `test_image.jpg`    |        `0.25` | Possible hidden data                |
| `suspect_image.png` |        `0.40` | Steganography likely present        |

The uploaded experiment instructs the user to review the scores and determine whether further investigation is required.

---

# 10. Document the Findings

Record the following information for each analyzed image:

* Image filename
* Image format
* Analysis date
* StegExpose score
* Interpretation
* Additional observations

Example:

```text
Image: suspect_image.png
Tool: StegExpose
Score: 0.40
Interpretation: Steganography likely present
```

---

# Result

The image was successfully analyzed using **StegExpose** to detect possible hidden data. The suspect score was obtained and used to determine whether steganography was likely to be present in the analyzed image, as specified in the experiment.


---

## Output Screenshots :
# Ex. No. 8 — Use StegExpose to Detect Hidden Data in Images

## Digital Forensics Lab

### Aim / Description

**StegExpose** is a tool used to detect possible hidden data in images using steganography analysis.

It works by evaluating the statistical properties of an image and producing a **suspect score** to estimate whether hidden data may be embedded in the image.

This experiment demonstrates how to install and run StegExpose, analyze individual images, perform batch analysis, and interpret the resulting suspect score.

---

# Prerequisites

The following are required:

* Java Runtime Environment (JRE)
* StegExpose
* Test images
* Command Prompt / Terminal

StegExpose is Java-based, so Java must be installed before running the tool.

---

# 1. Download and Set Up StegExpose

## 1.1 Download StegExpose

Download the **StegExpose `.jar` file** from the official GitHub repository.

The required file is:

```text
StegExpose.jar
```

---

## 1.2 Install Java

Install the Java Runtime Environment if Java is not already installed.

Verify Java installation using:

```bash
java -version
```

If Java is installed correctly, the installed Java version will be displayed.

---

## 1.3 Prepare the Working Directory

Create a folder for the experiment.

Example:

```text
StegExpose-Lab/
│
├── StegExpose.jar
├── test_image.png
└── results/
```

Place the downloaded `StegExpose.jar` file inside the working directory.

The original experiment specifies placing the `.jar` file in a folder where the image files will be analyzed.

---

# 2. Select Images for Analysis

Collect the images that need to be examined for possible hidden data.

StegExpose supports common image formats such as:

```text
.png
.jpg
.jpeg
.bmp
```

Example:

```text
images/
├── clean_image.png
├── test_image.jpg
└── suspect_image.bmp
```

The original experiment identifies PNG, JPG, and BMP as supported example image formats.

---

# 3. Open Command Prompt or Terminal

Open:

**Windows:**

```text
Command Prompt
```

or

**Linux/macOS:**

```text
Terminal
```

Navigate to the folder containing `StegExpose.jar`.

For Windows:

```bash
cd C:\StegExpose-Lab
```

For Linux/macOS:

```bash
cd ~/StegExpose-Lab
```

The lab procedure requires navigating to the directory containing the StegExpose JAR file before executing the commands.

---

# 4. Analyze a Single Image

Use the following command:

```bash
java -jar StegExpose.jar <image_file_path>
```

Example:

```bash
java -jar StegExpose.jar test_image.png
```

Replace:

```text
<image_file_path>
```

with the actual path of the image.

For example:

```bash
java -jar StegExpose.jar C:\StegExpose-Lab\images\suspect_image.png
```

The original experiment specifies this command for analyzing an individual image.

---

# 5. Analyze the Output

After the image has been analyzed, StegExpose provides a **suspect score**.

The score ranges between:

```text
0 and 1
```

A higher score indicates a greater likelihood that hidden data may be present according to the experiment's stated thresholds.

---

## Suspect Score Interpretation

|           Score | Interpretation               |
| --------------: | ---------------------------- |
| Less than `0.2` | Image is considered clean    |
|     `0.2 – 0.3` | Possible hidden data         |
|     Above `0.3` | Steganography likely present |

These threshold interpretations are the ones specified in the uploaded experiment.

> **Note:** A StegExpose score is a detection indicator, not proof by itself that an image contains hidden data. Further forensic examination may be required.

---

# 6. Example Output

Run:

```bash
java -jar StegExpose.jar suspect_image.png
```

Example output:

```text
Analyzing suspect_image.png...
Result: 0.4
Steganography likely present
```

The uploaded experiment provides this example output with a suspect score of `0.4`.

---

# 7. Batch Analysis

StegExpose can also analyze multiple images by specifying a folder.

Use:

```bash
java -jar StegExpose.jar <folder_path>
```

Example:

```bash
java -jar StegExpose.jar images
```

Or with an absolute path:

```bash
java -jar StegExpose.jar C:\StegExpose-Lab\images
```

Replace:

```text
<folder_path>
```

with the path containing the images to be analyzed.

The experiment specifies folder-based analysis for examining multiple images.

---

# 8. Advanced Options

StegExpose provides additional command-line options.

To view the available options, run:

```bash
java -jar StegExpose.jar --help
```

This can be used to examine available parameters such as sensitivity and output verbosity.

---

# 9. Review the Results

After analysis, review the score produced for each image.

Example:

```bash
java -jar StegExpose.jar suspect_image.png
```

Example result:

```text
Analyzing suspect_image.png...
Result: 0.4
Steganography likely present
```

Record the results for each analyzed image.

A simple result table can be maintained:

| Image               | Suspect Score | Interpretation                      |
| ------------------- | ------------: | ----------------------------------- |
| `clean_image.png`   |        `0.12` | Clean according to stated threshold |
| `test_image.jpg`    |        `0.25` | Possible hidden data                |
| `suspect_image.png` |        `0.40` | Steganography likely present        |

The uploaded experiment instructs the user to review the scores and determine whether further investigation is required.

---

# 10. Document the Findings

Record the following information for each analyzed image:

* Image filename
* Image format
* Analysis date
* StegExpose score
* Interpretation
* Additional observations

Example:

```text
Image: suspect_image.png
Tool: StegExpose
Score: 0.40
Interpretation: Steganography likely present
```

---

# Result

The image was successfully analyzed using **StegExpose** to detect possible hidden data. The suspect score was obtained and used to determine whether steganography was likely to be present in the analyzed image, as specified in the experiment.


---

## Output Screenshots :
<img width="1280" height="426" alt="WhatsApp Image 2026-09-21 at 9 58 02 PM" src="https://github.com/user-attachments/assets/a6557bb4-3a03-4882-a8a4-09c1e3237d5f" />
<img width="1280" height="720" alt="WhatsApp Image 2026-09-22 at 1 02 39 AM" src="https://github.com/user-attachments/assets/c1e70e06-ae59-4b4f-a17d-fe456332dd8a" />
<img width="1280" height="426" alt="WhatsApp Image 2026-09-21 at 9 58 03 PM (1)" src="https://github.com/user-attachments/assets/dcde2ba8-80c6-4af6-8f8d-3f5916771189" />
