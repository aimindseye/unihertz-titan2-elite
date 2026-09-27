# SableOS product handoff

Titan 2 Elite must be treated as an independent device profile. Titan 2 manual evidence and Titan 2 implementation decisions are useful references, but they do not prove Titan 2 Elite hardware capability.

## References

```text
PLATFORM_SABLE_PR_31=Toolbox / Hardware Utilities / Remote / Radio UX
PLATFORM_SABLE_PR_32=Private Space / Dual Apps / Work Profile / App Lock / Secure Vault UX
PLATFORM_SABLE_PR_33=Sub-screen / Shortcut Keys / Keyboard Gestures UX
PLATFORM_SABLE_PR_34=Mobile Manager / App Controls / Student Mode UX
PLATFORM_SABLE_PR_35=Connectivity / OTG / NFC / Cast / Compatibility UX
PLATFORM_SABLE_PR_36=Mobile Manager Network Authority Clarification
AIMINDSEYE_SABLEOS_HANDOFF=docs/TITAN2_MANUAL_PRODUCT_HANDOFF.md
```

## Non-inheritance rule

```text
TITAN2_ELITE_PROFILE=INDEPENDENT_VALIDATION_REQUIRED
TITAN2_PROFILE_PASS_INHERITANCE=NO
Q27_PROFILE_PASS_INHERITANCE=NO
```

The Elite implementation may reuse Sable common UX contracts, but every hardware claim must be proven on Titan 2 Elite retail hardware or a verified Elite firmware/device evidence set.

## Network Manager rule

Mobile Manager must reuse the same Sable Network Manager authority used by Panther/R9 and Titan 2. Do not implement a parallel network blocker in the Elite profile.

```text
MOBILE_MANAGER_REUSES_SABLE_NETWORK_MANAGER=YES
NETWORK_CONTROL_AUTHORITY=SETTINGS_OWNED_SABLE_NETWORK_MANAGER
NETWORK_CONTROL_IMPLEMENTATION=REVOCABLE_ANDROID_PERMISSION_INTERNET
ALL_NETWORK_TOGGLE=YES
DUPLICATE_NETWORK_BLOCKER=NO
DUPLICATE_NETWORK_POLICY_STORE=NO
PER_APP_CELLULAR_TOGGLE=NO_UNLESS_PLATFORM_ENFORCEMENT_PROVEN
PER_APP_WIFI_TOGGLE=NO_UNLESS_PLATFORM_ENFORCEMENT_PROVEN
```

## Elite validation gates

```text
TOOLBOX_SENSOR_MATRIX=REQUIRED
IR_TRANSMITTER=VERIFY_BEFORE_ENABLE
FM_TUNER_PATH=VERIFY_BEFORE_ENABLE
SUBSCREEN_CAPABILITY=VERIFY_BEFORE_ENABLE
PRIVATE_SPACE_DUAL_APPS_WORK_PROFILE=ANDROID_PROFILE_AND_STORAGE_MODEL_REQUIRED
USB_OTG_NFC_CAST=VERIFY_BEFORE_ENABLE
```
