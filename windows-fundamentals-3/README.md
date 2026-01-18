Windows Fundamentals 3 – Security Notes

Practical notes and security-focused explanations based on the Windows Fundamentals 3 room from TryHackMe.

Goal: Build a solid understanding of native Windows security controls and how they are relevant from a defensive and attacker (LOLBins) perspective.

🎯 Scope of this documentation

This repository documents the following Windows security components:

Windows Update

Windows Security overview

Virus & Threat Protection (Microsoft Defender)

Firewall & Network Protection

App & Browser Control (SmartScreen)

Device Security (Core Isolation, Memory Integrity, TPM)

BitLocker

Volume Shadow Copy Service (VSS)

The focus is understanding, not step‑by‑step lab answers.

🧱 Windows Update

Windows Update is Microsoft’s mechanism for distributing:

security patches

feature updates

Defender definition updates

Key points:

Updates are typically released on Patch Tuesday (2nd Tuesday of the month)

Critical patches can be released out of band

Keeping systems updated is a foundational security control

🛡️ Windows Security (Overview)

Windows Security centralizes built‑in protection features.

Status indicators:

🟢 Green: no action needed

🟡 Yellow: recommendations available

🔴 Red: immediate attention required

Protection areas:

Virus & threat protection

Firewall & network protection

App & browser control

Device security

🦠 Virus & Threat Protection (Microsoft Defender)

Microsoft Defender provides real‑time malware protection.

Key features

Real‑time protection – detects threats as they execute

Cloud‑delivered protection – faster detection using Microsoft intelligence

Automatic sample submission – improves global detection

Exclusions – reduces false positives (high risk if misused)

⚠️ Real‑time protection is sometimes disabled in labs/servers for performance reasons, but should be enabled on personal systems.

🔥 Firewall & Network Protection

Windows Defender Firewall controls network traffic, not file trust.

Firewall profiles:

Domain – authenticated corporate networks

Private – trusted home networks

Public – untrusted networks (airports, cafés, hotels)

Public networks apply the most restrictive rules.

🌐 App & Browser Control (SmartScreen)

Microsoft Defender SmartScreen protects users from:

phishing websites

malicious or untrusted downloads

suspicious applications

SmartScreen evaluates reputation, not signatures.

Settings:

Warn

Block

Off (not recommended)

SmartScreen often stops attacks before malware execution.

🖥️ Device Security
Core Isolation

Uses virtualization to isolate critical system processes.

Memory Integrity

Prevents malicious code injection into protected memory

Protects against kernel‑level attacks

TPM (Trusted Platform Module)

A hardware security chip used to:

store cryptographic keys securely

support BitLocker, Secure Boot, Windows Hello

Malware cannot directly access TPM‑protected secrets.

🔐 BitLocker

BitLocker provides full disk encryption.

Best protection when paired with TPM ≥ 1.2

Without TPM, BitLocker requires a startup key stored on a removable drive (USB)

Protects data if a device is lost, stolen, or offline‑tampered.

🕒 Volume Shadow Copy Service (VSS)

VSS creates point‑in‑time snapshots of data.

Capabilities:

Create restore points

Perform system restore

Recover previous file versions

Security note:

Ransomware commonly deletes shadow copies

VSS is not a backup replacement

Offline/off‑site backups remain critical

⚔️ Security Perspective: Living Off The Land (LOLBins)

Attackers frequently abuse legitimate Windows tools to evade detection.

Examples:

PowerShell

WMI

vssadmin

certutil

Understanding native Windows tools is essential for both defensive detection and offensive tradecraft.

📌 Learning Outcome

This documentation represents:

foundational Windows security knowledge

a base for Blue Team / SOC learning

preparation for deeper Windows internals and Active Directory topics

📚 References

Microsoft Documentation

TryHackMe – Windows Fundamentals

MITRE ATT&CK (Living Off The Land techniques)
