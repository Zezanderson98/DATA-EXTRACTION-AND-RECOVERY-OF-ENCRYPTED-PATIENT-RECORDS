# Mediroza General Hospital
# Penetration Testing Report

## Milestone 2 - Data Extraction and Recovery of Encrypted Patient Records

---

# Executive Summary

Following the successful acquisition of three confidential patient laboratory reports during Milestone 1, an assessment was conducted to evaluate the effectiveness of the encryption and password protection mechanisms safeguarding sensitive medical information.

The objective of this phase was to determine whether an attacker who obtained copies of the encrypted reports could recover access to the underlying contents using offline password recovery techniques.

Testing confirmed that all three encrypted PDF reports were vulnerable to password recovery attacks. Through authorized security testing, the passwords protecting each report were successfully recovered, resulting in unrestricted access to confidential patient information.

The assessment demonstrates that the confidentiality of the patient records relied heavily on passwords that could be recovered using readily available password-cracking techniques.

---

# Engagement Information

| Item | Description |
|--------|--------|
| Client | Mediroza General Hospital |
| Assessment Type | Black-Box Penetration Test |
| Assessment Phase | Milestone 2 - Data Extraction |
| Objective | Recover access to encrypted patient reports |
| Status | Completed |
| Outcome | Successful |

---

# Objective

Assess the effectiveness of password protection applied to sensitive patient laboratory reports and determine whether the encryption mechanisms could withstand offline password recovery attacks.

---

# Methodology

The following assessment methodology was performed:

1. Analyze the encryption method protecting each PDF document.
2. Extract password verification data where applicable.
3. Perform offline password recovery testing.
4. Validate recovered passwords.
5. Decrypt protected documents.
6. Review report contents.
7. Collect evidence for reporting purposes.

All testing was conducted under the authorized scope of the engagement.

---

# Finding MED-002

## Weak Password Protection on Sensitive Medical Records

### Severity

**HIGH**

### Risk Rating

**HIGH**

### Attack Vector

Offline Password Recovery

### Affected Assets

- Patient Report 1
- Patient Report 2
- Patient Report 3

---

# Technical Analysis

## Patient Report 1

### Assessment Overview

The first patient laboratory report was identified as an encrypted PDF document containing sensitive medical information.

The objective was to determine whether the applied password protection could resist offline password recovery attempts.

### Attack Path

The document was uploaded to the **Networkwalks Hash Calculator**, which was used to extract the password verification hash embedded within the protected PDF.

Once the hash was successfully extracted, it was submitted to the **Networkwalks Password Cracker** for password recovery testing.

The password cracker performed a dictionary-based attack against the extracted hash and successfully identified the correct password associated with the document.

The recovered password was then used to unlock the PDF and verify access to the protected contents.

### Tools Used

- Networkwalks Hash Calculator
- Networkwalks Password Cracker

### Result

✅ Password successfully recovered

✅ Document successfully decrypted

✅ Patient information successfully accessed

---

## Patient Report 2

### Assessment Overview

The second patient report was assessed using the same methodology to determine the effectiveness of its password protection controls.

### Attack Path

The encrypted PDF was analyzed using the **Networkwalks Hash Calculator**.

The tool extracted the password verification hash from the file, enabling offline password recovery testing.

The extracted hash was submitted to the **Networkwalks Password Cracker**, which performed dictionary-based password recovery operations against the encrypted credential material.

The attack successfully recovered the correct password protecting the report.

After password recovery, the PDF was opened and the document contents were successfully reviewed.

### Tools Used

- Networkwalks Hash Calculator
- Networkwalks Password Cracker

### Result

✅ Password successfully recovered

✅ Document successfully decrypted

✅ Patient information successfully accessed

---

## Patient Report 3

### Assessment Overview

The third encrypted patient report required an alternative password recovery methodology.

Initial analysis indicated that a different approach would be more appropriate given the characteristics of the document.

### Attack Path

The encrypted PDF was subjected to offline password recovery testing using **PDFCrack**, an open-source PDF password recovery utility.

A large password corpus, specifically the **RockYou** wordlist, was supplied to support a dictionary-based attack against the protected file.

PDFCrack systematically tested password candidates contained within the RockYou wordlist against the document's encryption mechanism.

The password was successfully recovered and subsequently validated by opening the protected report.

Following successful authentication, full access to the patient report contents was obtained.

### Tools Used

- PDFCrack
- RockYou Wordlist

### Result

✅ Password successfully recovered

✅ Document successfully decrypted

✅ Patient information successfully accessed

---

# Evidence



---

## Patient Report 1 Evidence

### Evidence 1 – Hash Extraction

SS03-HASH-CALCULATOR-EXTRACTED-PDF-1-HASH




Networkwalks Hash Calculator displaying the extracted PDF hash.











<img width="1366" height="768" alt="SS03-COPY-HASH-PATIENT-PDF-1" src="https://github.com/user-attachments/assets/613d0e7d-37fd-405c-aa95-b34db11ff2d2" />







### Evidence 2 – Password Recovery

SS04-PASSWORD-CRACKER-RECOVERS-PDF-1-PASSWORD




Networkwalks Password Cracker successfully recovers the document password.


<img width="1366" height="768" alt="SS07-PDF-PASSWORD-FOR-PATIENT-1-CRACKED-SUCESSFULLY" src="https://github.com/user-attachments/assets/47158de7-6183-4429-b654-ec28e339bab4" />









### Evidence 3 – Successful Access

SS05-ACCESSING-PDF-1-PATIENT_REPORT






Patient Report 1 opened after entering the recovered password.




<img width="1366" height="768" alt="SS08-ACCESSING-PDF-1-PATIENT_REPORT" src="https://github.com/user-attachments/assets/8e1b3b82-4acb-4337-ad81-fbe6284883ee" />





### Evidence 4 – Report Contents

SS06-PDF-1-PATIENT_REPORT-ACCESSED






Recovered patient laboratory report contents.


<img width="1366" height="768" alt="SS09-PDF-1-PATIENT _REPORT- ACCESSED SUCESSFULY" src="https://github.com/user-attachments/assets/887f915a-8cb3-4a2e-b46f-8cd855c9e865" />





---

## Patient Report 2 Evidence

### Evidence 5 – Hash Extraction

SS03-HASH-CALCULATOR-EXTRACTED-PDF-2-HASH






Networkwalks Hash Calculator displaying the extracted the PDF 2 hash.



<img width="1366" height="768" alt="SS03-COPY-HASH-PATIENT-PDF-2" src="https://github.com/user-attachments/assets/d83491c0-287e-4877-af03-de556abcd575" />








### Evidence 6 – Password Recovery

SS04-PASSWORD-CRACKER-RECOVERS-PDF-2-PASSWORD




Networkwalks Password Cracker displaying successful password recovery.



<img width="1366" height="768" alt="SS07-PDF-PASSWORD-FOR-PATIENT-2-CRACKED-SUCESSFULY" src="https://github.com/user-attachments/assets/19d16626-e198-4ba0-b122-680d2dfe40e1" />








### Evidence 7 – Successful Access

SS05-ACCESSING-PDF-2-PATIENT_REPORT





Patient Report 2 opened using the recovered password.



<img width="1366" height="768" alt="SS08-ACCESSING-PDF-2-PATIENT_REPORT" src="https://github.com/user-attachments/assets/e0ccbf63-1222-4796-825f-956ef852d0c5" />





### Evidence 8 – Report Contents

SS06-PDF-2-PATIENT_REPORT-ACCESSED




Recovered patient laboratory report contents.



<img width="1366" height="768" alt="SS09-PDF-2-PATIENT_REPORT-ACCESSED-SUCESSFULY" src="https://github.com/user-attachments/assets/17de8b33-610f-4827-92bd-907e8f355aca" />








---

## Patient Report 3 Evidence

### Evidence 9 – PDFCrack Execution

SS01_PDFCRACK_ROCKYYOU_PATIENT_REPORT_3







PDFCrack terminal output showing successful password recovery using the RockYou wordlist.







<img width="1360" height="662" alt="SS01_PDFCRACK_ROCKYYOU_PATIENT_REPORT_3" src="https://github.com/user-attachments/assets/c949e212-2a8c-4398-ade6-e1cf0d2db77a" />




### Evidence 10 – Successful Access

SS02-ACCESSING-PDF-3-PATIENT_REPORT








Patient Report 3 opened after decryption.






<img width="1366" height="768" alt="SS02-ACCESSING-PDF-3-PATIENT_REPORT" src="https://github.com/user-attachments/assets/b7bfe1bb-cff1-4c6c-932c-537fd143591e" />



### Evidence 11 – Report Contents

SS03-PDF-3-PATIENT_REPORT-ACCESSED







Recovered patient laboratory report contents.





<img width="1366" height="768" alt="SS03-PDF-3-PATIENT_REPORT-ACCESSED" src="https://github.com/user-attachments/assets/1acf182f-5ccb-4ca4-8d08-80da2ac10957" />


---

# Security Impact

The successful recovery of passwords from all three encrypted reports demonstrates inadequate protection of sensitive medical records.

An attacker obtaining access to these files would not require access to the hospital infrastructure, web application, or authentication systems in order to compromise the underlying data.

Potential consequences include:

- Unauthorized disclosure of patient records
- Exposure of Personally Identifiable Information (PII)
- Loss of patient confidentiality
- Regulatory and compliance violations
- Legal liability
- Reputational damage

The risk is increased because the attack can be performed entirely offline, making detection significantly more difficult.

---

# Root Cause

The affected documents relied on passwords that were susceptible to dictionary-based recovery attacks.

Contributing factors include:

- Weak password selection
- Insufficient password complexity requirements
- Lack of password strength enforcement
- Overreliance on password-protected PDFs as a security control

---

# Risk Assessment

| Metric | Rating |
|----------|----------|
| Likelihood | High |
| Impact | High |
| Attack Complexity | Low |
| Privileges Required | None |
| User Interaction | None |
| Confidentiality Impact | High |
| Integrity Impact | Low |
| Availability Impact | None |
| Overall Severity | High |

---

# Recommendations

## Immediate Actions

1. Replace passwords protecting all sensitive patient reports.
2. Review existing exported documents for weak password usage.
3. Re-issue sensitive documents protected by stronger credentials.

## Short-Term Improvements

1. Enforce minimum password length requirements.
2. Require complex passphrases rather than common dictionary words.
3. Implement password strength validation controls.
4. Restrict unnecessary distribution of exported reports.

## Long-Term Improvements

1. Implement centralized document management systems.
2. Migrate sensitive medical records to role-based access control platforms.
3. Introduce data loss prevention (DLP) controls.
4. Enable auditing and monitoring of patient report access.
5. Conduct routine security assessments of document protection controls.

---

# Conclusion

This assessment confirmed that all three encrypted patient laboratory reports were vulnerable to offline password recovery attacks.

For Patient Reports 1 and 2, password verification hashes were extracted using the Networkwalks Hash Calculator and successfully cracked using the Networkwalks Password Cracker.

For Patient Report 3, password recovery was achieved using PDFCrack in conjunction with the RockYou password corpus.

In all three cases, the recovered credentials enabled complete access to confidential patient information contained within the protected reports.

The identified weakness represents a High-Severity confidentiality risk and should be remediated through stronger password policies, improved document security controls, and enhanced access management practices.

---

# Assessment Outcome

| Objective | Status |
|------------|------------|
| Recover Patient Report 1 | ✅ Successful |
| Recover Patient Report 2 | ✅ Successful |
| Recover Patient Report 3 | ✅ Successful |
| Validate Recovered Passwords | ✅ Successful |
| Access Protected Contents | ✅ Successful |
| Collect Evidence | ✅ Successful |
| Complete Milestone 2 | ✅ Complete |

---




**Next Phase** Milestone 3: Critical Data Exposure Assessment



##  👤 Author

**Anderson Edaiyo Uzezi**  
Cybersecurity Professional B084  
LinkedIn: https://www.linkedin.com/in/anderson-edaiyo-bab74117b
