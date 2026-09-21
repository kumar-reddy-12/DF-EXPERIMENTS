# Ex. No. 7 — Use AFLogical OSE to Extract Data from an Android Device

## Digital Forensics Lab

### Aim 

**AFLogical OSE (Open Source Edition)** is a tool used to extract data from Android devices. It is part of the Open Source Android Forensics project and performs **logical extraction** of Android data.

The experiment demonstrates how to connect an Android device to a computer using **Android Debug Bridge (ADB)**, install AFLogical OSE, extract forensic data, transfer the extracted files to a computer, and analyze the resulting CSV files.

The extracted information may include:

* Contacts
* SMS
* MMS
* Call Logs

AFLogical OSE performs logical extraction without directly accessing the Android file system.

---

# Requirements

The following software and equipment are required:

* Windows / macOS / Linux computer
* Android device
* USB cable
* Java
* Android Debug Bridge (ADB)
* AFLogical OSE
* USB debugging enabled Android device

---

# Procedure

## 1. Prepare the Environment

### 1.1 Download AFLogical OSE

Download AFLogical OSE from its GitHub repository or obtain the required release package.

Alternatively, clone the repository using Git.

---

## 1.2 Install Java

AFLogical OSE requires Java to run.

Install Java if it is not already available on the computer.

Verify the installation using:

```bash
java -version
```

If Java is installed correctly, the installed Java version will be displayed.

The original experiment specifies Java as one of the required components for AFLogical OSE.

---

## 1.3 Install Android Debug Bridge

**Android Debug Bridge (ADB)** is a command-line tool used to communicate with an Android device.

After installing ADB, verify it using:

```bash
adb version
```

If required, add the ADB installation directory to the system `PATH` environment variable.

---

# 2. Enable USB Debugging

On the Android device:

1. Open **Settings**.
2. Open **About Phone**.
3. Locate **Build Number**.
4. Tap **Build Number** seven times.
5. Developer Options will be enabled.
6. Go to **Settings → Developer Options**.
7. Enable **USB Debugging**.

The lab procedure specifies enabling Developer Options by tapping Build Number seven times and then enabling USB Debugging.

<img width="1280" height="426" alt="WhatsApp Image 2026-09-21 at 9 57 58 PM (1)" src="https://github.com/user-attachments/assets/9d401c57-352f-4f7d-86e4-2c2ffbfdf3b8" />


# 3. Connect the Android Device

## 3.1 Connect via USB

Connect the Android device to the computer using a USB cable.

If the Android device displays an authorization prompt such as:

```text
Allow USB debugging?
```

Review the prompt and authorize the computer if appropriate for the forensic examination.

---

## 3.2 Verify the ADB Connection

Open **Command Prompt** or **Terminal** and run:

```bash
adb devices
```

Example output:

```text
List of devices attached
XXXXXXXX    device
```

If the device appears with the status:

```text
device
```

the ADB connection is ready.

If the device is not listed:

* Check that USB debugging is enabled.
* Check the USB cable.
* Check the Android USB drivers.
* Reconnect the device.
* Confirm the USB debugging authorization prompt.

The original experiment uses `adb devices` to verify the connected Android device.

<img width="1280" height="677" alt="WhatsApp Image 2026-09-22 at 12 57 30 AM" src="https://github.com/user-attachments/assets/ce1267c1-9423-49e6-ad99-d27df3bba1b1" />


# 4. Extract Data Using AFLogical OSE

## 4.1 Locate AFLogical OSE

Navigate to the directory where AFLogical OSE has been downloaded or extracted.

Example:

```bash
cd C:\AFLogical
```

---

## 4.2 Install AFLogical OSE APK

Install the AFLogical application on the Android device using ADB.

Run:

```bash
adb install aflogical.apk
```

If the installation is successful, the AFLogical application will be installed on the Android device.

The lab procedure specifies installing the APK using this ADB command.

<img width="1280" height="743" alt="WhatsApp Image 2026-09-22 at 12 55 01 AM" src="https://github.com/user-attachments/assets/f2e44443-74ac-41e7-894a-f57886e812fa" />


# 5. Launch AFLogical OSE

On the Android device:

1. Open the **AFLogical** application.
2. Review the available extraction options.
3. Select the required data types.

Typical extraction categories include:

```text
Contacts
SMS
MMS
Call Logs
```

The experiment specifically identifies contacts, SMS, MMS, and call logs as examples of data that can be selected for extraction.

<img width="1280" height="546" alt="WhatsApp Image 2026-09-22 at 12 42 31 AM" src="https://github.com/user-attachments/assets/f255cae9-c2f0-44a2-860d-4919fd0261f9" />


# 6. Start Data Extraction

After selecting the required data types:

1. Start the extraction process.
2. Wait for AFLogical OSE to complete the extraction.
3. The extracted information will be stored as CSV files.
4. The data is typically stored in an `aflogical` directory on the Android device.

Example:

```text
aflogical/
├── contacts.csv
├── sms.csv
├── mms.csv
└── call_logs.csv
```

The exact filenames may vary depending on the Android device and AFLogical OSE version.

The original lab specifies that extracted data is stored in `.csv` files, typically under an `aflogical` directory.

---

# 7. Transfer Extracted Data to the Computer

## 7.1 Pull the Extracted Data

Use ADB to copy the extracted forensic data from the Android device to the computer.

Run:

```bash
adb pull /sdcard/aflogical /path/to/destination
```

For example, on Windows:

```bash
adb pull /sdcard/aflogical C:\Android_Forensics
```

Replace the destination path with the directory where the extracted evidence should be stored.

The lab procedure uses `adb pull` to transfer the extracted AFLogical data to the computer.

---

# 8. Verify the Extracted Data

Navigate to the destination directory:

```bash
cd C:\Android_Forensics
```

Check the extracted files.

Example:

```text
Android_Forensics/
└── aflogical/
    ├── contacts.csv
    ├── sms.csv
    ├── mms.csv
    └── call_logs.csv
```

Verify that the required CSV files have been successfully transferred.

The original procedure recommends checking the destination directory and verifying the extracted CSV files.

---

# 9. Analyze the Extracted Data

The extracted CSV files can be opened using:

* Microsoft Excel
* Google Sheets
* LibreOffice Calc
* Text Editor

Example:

```text
contacts.csv
sms.csv
mms.csv
call_logs.csv
```

---

## 9.1 Contacts Analysis

The contacts CSV file can be examined to identify:

* Contact names
* Phone numbers
* Other available contact information

---

## 9.2 SMS Analysis

The SMS data can be reviewed for:

* Sender information
* Recipient information
* Message content
* Available timestamps

---

## 9.3 MMS Analysis

The MMS data can be examined for available multimedia message information.

---

## 9.4 Call Log Analysis

The call log data can be reviewed for available:

* Phone numbers
* Call types
* Call times
* Call duration

The lab document specifies reviewing extracted contacts, SMS, MMS, and call-log data during analysis.

---

# 10. Document the Findings

After analyzing the extracted data:

1. Identify relevant forensic information.
2. Record important observations.
3. Preserve the extracted CSV files.
4. Prepare a forensic report if required.
5. Maintain the integrity of the extracted evidence.

A report can include:

```text
Device Information
Extraction Method
Extracted Data
Contacts
SMS
MMS
Call Logs
Observations
Conclusion
```

---

# 11. Clean Up

## 11.1 Uninstall AFLogical OSE

After completing the forensic extraction, AFLogical OSE can be removed from the Android device.

Run:

```bash
adb uninstall com.viaforensics.android.aflogical
```

The package name specified in the original experiment is:

```text
com.viaforensics.android.aflogical
```

---

## 11.2 Disconnect the Android Device

After completing the extraction and cleanup:

1. Close the forensic applications.
2. Safely disconnect the Android device.
3. Preserve the extracted evidence and reports.

The original experiment concludes by safely disconnecting the Android device after extraction.

---

# Result

The Android device was successfully connected to the computer using **ADB**, and **AFLogical OSE** was used to perform logical extraction of available Android data. The extracted contacts, SMS, MMS, and call-log information was transferred to the computer as CSV files for further forensic analysis and documentation.
