Project 02 – Windows Troubleshooting and System Repair

1. Project Overview

This project focuses on diagnosing Windows performance and system integrity issues using built-in Windows troubleshooting tools.

The objective was to inspect system resources, review Windows event logs, identify potential issues, and perform system repairs.

2. Environment

* Device: HP ProBook 450 G7
* Operating System: Windows 11 Professional
* RAM: 8 GB
* Storage: 239 GB SSD
* Processor: Intel Core i5-10210U

3. Tools Used

* Task Manager
* Event Viewer
* System Information (msinfo32)
* TPM Management (tpm.msc)
* System File Checker (sfc)
* Deployment Image Servicing and Management (DISM)

4. Troubleshooting Process

A. Performance Analysis

Used Task Manager to inspect CPU, memory, disk activity, and startup applications.

Findings:

* CPU usage was low during inspection.
* No apparent RAM saturation.
* SSD activity was low.
* Disabled unnecessary startup applications to reduce startup load.

B. Event Viewer Analysis

Reviewed Windows System logs and identified:

* Source: DistributedCOM
* Event ID: 10016
* Level: Warning

Also identified:

* Source: TPM-WMI
* Event ID: 1796
* Description: Secure Boot update failed while attempting to update SBAT.
* Error code: 0x800700c1

These events were documented for monitoring. No unnecessary system or firmware changes were made.

C. TPM and Secure Boot Verification

Used msinfo32 and tpm.msc to verify security configuration.

Results:

* BIOS Mode: UEFI
* Secure Boot: Enabled
* TPM Specification Version: 2.0
* TPM Status: Ready for use

D. Windows System Integrity Check

Executed:

sfc /scannow

Result:
Windows Resource Protection did not find any integrity violations.

E. Windows Component Store Diagnosis

Executed:

DISM /Online /Cleanup-Image /ScanHealth

Result:
The component store was found to be repairable.

F. Windows Component Store Repair

Executed:

DISM /Online /Cleanup-Image /RestoreHealth

Result:
The restore operation completed successfully.

G. Final System Integrity Verification

Executed sfc /scannow again after the DISM repair.

Result:
Windows Resource Protection did not find any integrity violations.

5. Final Outcome

* Inspected system performance and startup applications.
* Reviewed Windows event logs.
* Verified TPM 2.0 and Secure Boot configuration.
* Detected a repairable component store issue.
* Successfully repaired the Windows component store using DISM.
* Confirmed system file integrity using SFC.

6. Skills Practiced

* Windows troubleshooting
* Event Viewer analysis
* System performance monitoring
* TPM and Secure Boot verification
* Command-line diagnostics
* Windows image repair using DISM
* System integrity verification using SFC

7. Project Type

Personal hands-on IT support lab.

This project was completed in a personal Windows 11 environment for practical learning and portfolio development.
