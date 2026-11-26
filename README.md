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

The following evidence should be included within the report.

---

## Patient Report 1 Evidence

### Evidence 1 – Hash Extraction

**Insert Screenshot:**
Networkwalks Hash Calculator displaying the extracted PDF hash.

### Evidence 2 – Password Recovery

**Insert Screenshot:**
Networkwalks Password Cracker successfully recovering the document password.

### Evidence 3 – Successful Access

**Insert Screenshot:**
Patient Report 1 opened after entering the recovered password.

### Evidence 4 – Report Contents

**Insert Screenshot:**
Recovered patient laboratory report contents.

---

## Patient Report 2 Evidence

### Evidence 5 – Hash Extraction

**Insert Screenshot:**
Networkwalks Hash Calculator extracting the PDF hash.

### Evidence 6 – Password Recovery

**Insert Screenshot:**
Networkwalks Password Cracker displaying successful password recovery.

### Evidence 7 – Successful Access

**Insert Screenshot:**
Patient Report 2 opened using the recovered password.

### Evidence 8 – Report Contents

**Insert Screenshot:**
Recovered patient laboratory report contents.

---

## Patient Report 3 Evidence

### Evidence 9 – PDFCrack Execution

**Insert Screenshot:**
PDFCrack terminal output showing successful password recovery using the RockYou wordlist.

### Evidence 10 – Password Validation

**Insert Screenshot:**
Password used to successfully unlock the document.

### Evidence 11 – Successful Access

**Insert Screenshot:**
Patient Report 3 opened after decryption.

### Evidence 12 – Report Contents

**Insert Screenshot:**
Recovered patient laboratory report contents.

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
