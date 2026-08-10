# DF-EXPERIMENTS
# Experiment 1: Evidence Acquisition Using AccessData FTK Imager

## Aim

To acquire a forensic disk image from a physical storage device using AccessData FTK Imager and verify the integrity of the acquired image using MD5 and SHA1 hash values.

## Software Used

- AccessData FTK Imager 4.7.1.2
- Windows

## Introduction

FTK Imager is a computer forensic tool developed by AccessData. It is used for acquiring and analyzing digital forensic evidence.

FTK Imager can acquire:

- Volatile memory (RAM)
- Non-volatile memory such as hard disks and USB drives
- Physical drives
- Logical drives
- Image files
- Contents of folders
- CDs/DVDs

In this experiment, a physical USB storage device was acquired and converted into a forensic disk image.

## Procedure

### Step 1: Open FTK Imager

Open **AccessData FTK Imager 4.7.1.2**.

Navigate to the option for creating a disk image.


### Step 2: Select Evidence Source

Select **Physical Drive** and click **Next**.


### Step 3: Select Physical Drive

Select the physical drive that needs to be acquired.

The device used in this experiment was:

**SanDisk Cruzer Blade USB Device**

Click **Finish**.


### Step 4: Select Image Type

Select **Raw (dd)** and click **Next**.


### Step 5: Enter Evidence Information

The following evidence information was entered:

- Case Number: 1
- Evidence Number: 1
- Unique Description: DF
- Examiner: THUMMALA KUMAR REDDY
- Notes: EXP 1

Click **Next**.



### Step 6: Select Image Destination

The image was saved in the following destination:

`D:\3-1\Digital Forensics`

Image Filename:

`diskimage`

Image Fragment Size:

`0 MB`


### Step 7: Create Image

The source and destination information were displayed.

The option **Verify images after they are created** was selected.

Click **Start** to begin the acquisition.


### Step 8: Image Acquisition

FTK Imager started creating the forensic image from the physical drive.


### Step 9: Image Verification

After acquisition, FTK Imager verified the created forensic image.

The verification process checks the integrity of the acquired image using hash values.


### Step 10: Verification Result

The verification result showed:

- MD5 Verify Result: **Match**
- SHA1 Verify Result: **Match**
- Bad Blocks: **No bad blocks found in image**


### Step 11: Image Summary

The image summary provided details about the acquired physical drive.

Important information included:

- Source Type: Physical
- Drive Model: SanDisk Cruzer Blade USB Device
- Drive Interface Type: USB
- Source Data Size: 59112 MB
- Sector Count: 121061376
- Bytes per Sector: 512


### Step 12: Hash Verification

The image summary showed that the computed and reported hash values matched.

**MD5:**

`9f1f7659712cde7bc536dd82f341b5ce`

**SHA1:**

`abaca319c85c310078f410c02f6b11951af63334`

Both verification results were **Match**.


## Result

The physical USB drive was successfully acquired using **AccessData FTK Imager 4.7.1.2** and converted into a **Raw (dd) forensic image**.

The acquired image was successfully verified using MD5 and SHA1 hash values.

## Verification Results

| Parameter | Result |
|---|---|
| Image Type | Raw (dd) |
| Source | Physical Drive |
| Device | SanDisk Cruzer Blade USB Device |
| Source Size | 59112 MB |
| MD5 Verification | Match |
| SHA1 Verification | Match |
| Bad Blocks | No bad blocks found |

 <img width="1600" height="899" alt="image" src="https://github.com/user-attachments/assets/cfcc23cd-1ae9-42c4-8586-e39d061a44c5" />
<img width="1600" height="806" alt="image" src="https://github.com/user-attachments/assets/772cd976-aacc-4f06-994e-da38b08ed465" />
<img width="1600" height="770" alt="image" src="https://github.com/user-attachments/assets/f3599f54-d2b9-450d-a6a0-024e01058451" />
<img width="730" height="590" alt="image" src="https://github.com/user-attachments/assets/454810e6-4f01-48e5-b403-d3ea8e57b1d1" />
<img width="658" height="594" alt="image" src="https://github.com/user-attachments/assets/8497a412-0885-4aca-9d6a-2240e8afa627" />
<img width="735" height="541" alt="image" src="https://github.com/user-attachments/assets/8c659357-bed4-42c1-91a4-51b641745d9a" />
<img width="621" height="574" alt="image" src="https://github.com/user-attachments/assets/486e1310-33a4-485f-90c8-ca24885a9e10" />
<img width="658" height="449" alt="image" src="https://github.com/user-attachments/assets/9406b92f-3f82-4615-92da-620bc428bdc7" />
<img width="643" height="536" alt="image" src="https://github.com/user-attachments/assets/13ebe659-17ca-4275-b553-3aece19140a4" />
<img width="1600" height="847" alt="image" src="https://github.com/user-attachments/assets/0f094205-5937-4ec6-8fd4-fc613764d63e" />
