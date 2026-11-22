# Defender Control Remover

Focused workstation utility and PowerShell toolkit for managing Microsoft Defender real-time protection, SmartScreen reputation prompts, and developer folder exclusions without hunting through buried Group Policy trees.

<img width="512" height="512" alt="images1" src="https://github.com/user-attachments/assets/e9355602-5d4b-4ebb-bd39-91960039de3d" />
<img width="1082" height="647" alt="images2" src="https://github.com/user-attachments/assets/ed04e2f6-698e-4fca-a69d-0a9d4dbe82ee" />

## Antivirus Policy & Exclusion Controls

Built for local lab machines, compile servers, and gaming rigs where aggressive real-time scanning stalls builds or flags unsigned tools. Every change is reversible with a single toggle.

| Control Module | Target Component | Reversible |
| --- | --- | --- |
| Real-Time Monitor Switch | `MsMpEng.exe` live file-access hooks | Yes |
| Path & Process Exclusions | Dev workspaces, build outputs, mod loaders | Yes |
| SmartScreen Gate | App and browser reputation filter | Yes |
| Tamper Check Helper | Status audit before applying policy edits | Yes |


<img width="687" height="291" alt="images3" src="https://github.com/user-attachments/assets/076b0a52-a962-4c11-969b-f55591c27647" />


## PowerShell Automation Examples

```powershell
# Add a local build directory to Defender exclusions
Add-MpPreference -ExclusionPath "D:\builds\workspace"

# Inspect current real-time protection status
Get-MpComputerStatus | Select-Object RealTimeProtectionEnabled, IsTamperProtected
```


<img width="375" height="57" alt="images4" src="https://github.com/user-attachments/assets/0965e5cf-6a88-4add-86ca-c0ebcde9ceac" />


## Safe Usage & Rollback Guide

1. Run the launcher with Administrator privileges so policy queries return accurate state.
2. If Tamper Protection is locked in Security Center, disable it manually first before toggling real-time monitoring.
3. Prefer targeted folder exclusions over a full antivirus shutdown on daily-driver machines.
4. Click **Restore Defaults** at any time to re-enable standard Microsoft Defender protection and clear custom rules.


<img width="782" height="319" alt="images5" src="https://github.com/user-attachments/assets/54c3c662-da61-4685-b1a7-1827b84d380c" />
