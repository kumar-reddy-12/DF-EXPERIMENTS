<img width="1920" height="1080" alt="Screenshot 2026-08-24 112226" src="https://github.com/user-attachments/assets/98566b77-2f2c-422e-a114-b7856a1b70ed" /># Experiment No. 4: Analyze Email Headers and Detect Email Spoofing Using MHA

## Aim

To analyze an email header using Mail Header Analyzer (MHA) and detect possible email spoofing by examining email routing information and authentication results.

## Requirements

* Gmail / Outlook / Yahoo Mail
* Mail Header Analyzer (MHA)
* Web browser
* WHOIS / IP lookup tool
* Internet connection

## Procedure

### Step 1: Access the Email Header

**Gmail:**

1. Open the email.
2. Click the three-dot menu in the upper-right corner.
3. Select **Show original**.

**Outlook:**

1. Open the email.
2. Click **File**.
3. Select **Properties**.
4. Locate the **Internet headers** section.

**Yahoo:**

1. Open the email.
2. Click the three-dot menu.
3. Select **View raw message**.

### Step 2: Copy the Email Header

Copy the complete email header displayed by the email service.

### Step 3: Analyze the Header Using MHA

1. Open Mail Header Analyzer.
2. Paste the copied email header into the analyzer.
3. Submit the header for analysis.
4. Examine the parsed header information.
5. Identify the `From`, `To`, `Return-Path`, `Received`, and `Message-ID` fields.
6. Check the SPF, DKIM, and DMARC authentication results.

### Step 4: Analyze the Received Fields

Examine the `Received` fields to determine:

* Sending server hostname
* Sending server IP address
* Receiving server
* Date and time of transmission
* Sequence of mail servers

The `Received` headers should be analyzed from the **bottom upward** to trace the email's path.

### Step 5: Check IP Addresses and Hostnames

Use an IP lookup or WHOIS tool to check the IP addresses found in the `Received` headers.

Verify whether:

* The IP belongs to the expected mail server.
* The hostname matches the IP address.
* The sending server appears legitimate.
* Any unexpected server or IP address is present.

### Step 6: Check SPF, DKIM, and DMARC

Record the authentication results.

| Check | Result    | Observation                                |
| ----- | --------- | ------------------------------------------ |
| SPF   | PASS/FAIL | Check whether the sending IP is authorized |
| DKIM  | PASS/FAIL | Check whether the DKIM signature is valid  |
| DMARC | PASS/FAIL | Check domain authentication and alignment  |

### Step 7: Analyze Message-ID

Check the domain used in the `Message-ID` and compare it with the sender's domain.

### Step 8: Identify Possible Spoofing Indicators

Check for:

* `From` and `Return-Path` domain mismatch
* Suspicious IP addresses
* Unexpected hostnames
* SPF failure
* DKIM failure
* DMARC failure
* Unusual timestamps
* Inconsistent mail-server routing
* Suspicious Message-ID domain

## Sample Header

```text
Received: from mail.example.com (mail.example.com [192.0.2.1])
  by mail.receiver.com with ESMTP id u29si8604336pjs.40.2023.08.10.07.00.16;
  Thu, 10 Aug 2023 07:00:16 -0700 (PDT)

Received: by mail.example.com with SMTP id a1mr1243772ywh.51;
  Thu, 10 Aug 2023 07:00:15 -0700 (PDT)

Message-ID: <CA+7eu=4pSeXgQ@mail.example.com>
```

## Analysis

* The email passed through `mail.example.com` before reaching `mail.receiver.com`.
* The sending IP address shown is `192.0.2.1`.
* The timestamps in the `Received` fields are in logical chronological order.
* The `Message-ID` contains the `mail.example.com` domain.
* SPF, DKIM, and DMARC results should be checked in the actual email header.
* Any authentication failure combined with domain or IP inconsistencies should be investigated as a possible spoofing attempt.

## Observation

The email header was successfully parsed using MHA. The sender information, mail-server path, IP address, Message-ID, and email authentication results were examined for inconsistencies.

## Result

The email header was successfully analyzed using Mail Header Analyzer, and possible email spoofing indicators were identified by examining the **Received, Return-Path, Message-ID, SPF, DKIM, and DMARC** fields.

## Conclusion

Email header analysis using MHA can be used to trace the email's delivery path and identify inconsistencies that may indicate email spoofing or phishing.

<img width="1920" height="1080" alt="Screenshot 2026-08-24 111717" src="https://github.com/user-attachments/assets/f406de4d-37c3-4b6e-b42d-360c23b9a0c9" />
<img width="1920" height="1080" alt="Screenshot 2026-08-24 112118" src="https://github.com/user-attachments/assets/06fcc906-d304-433a-92c6-65234b2ff2a7" />
<img width="1920" height="1080" alt="Screenshot 2026-08-24 112143" src="https://github.com/user-attachments/assets/96f14dfb-015f-4d42-b557-b34d17d30a49" />
<img width="1920" height="1080" alt="Screenshot 2026-08-24 112159" src="https://github.com/user-attachments/assets/7ca19725-dddd-43eb-b567-194d7e6a5eb2" />
<img width="1920" height="1080" alt="Screenshot 2026-08-24 112213" src="https://github.com/user-attachments/assets/df62bab6-4f6a-4bea-a678-7882ded8499e" />
<img width="1920" height="1080" alt="Screenshot 2026-08-24 112254" src="https://github.com/user-attachments/assets/60bb1dc8-2127-4a12-984b-f912d7b6fd0a" />
<img width="1920" height="1080" alt="Screenshot 2026-08-24 112544" src="https://github.com/user-attachments/assets/901c7c49-20fb-4d9d-9bfd-b00519a86959" />
<img width="1920" height="1080" alt="Screenshot 2026-08-24 112846" src="https://github.com/user-attachments/assets/1f5ea52b-6ea7-44a6-8196-c38f8e47984c" />
<img width="1920" height="1080" alt="Screenshot 2026-08-24 112927" src="https://github.com/user-attachments/assets/ed3ee36b-d009-48f1-9ebd-26e9eb808e11" />





