# Secure Enclave

The Secure Enclave is a key concept in the security model of the MajorPrivacy process, designed to explicitly isolate it from external untrusted applications through multi-layered protection.
You can configure related settings in the <a href="../Panel/Secure Enclave.md">Secure Enclave Panel</a>.

The enclave itself typically has the following configuration sections:
1. Enclave Name
2. Enclave Comment
3. Code Integrity Preset
4. Process Creation Handling
5. Other Options

Below, we will explain the configuration sections 3, 4, and 5 in detail.

The Code Integrity Preset consists of the following configurations:
 - **Required Signature**: All applications running within the enclave must meet the digital signature level specified in this configuration item. For the initiating process, if the requirements are not met, it will be "Ejected" from the enclave. For child processes, the settings in "Process Creation Handling" will be applied. If Image Load Protection is enabled, modules loaded by the application will also be subject to this restriction.
   - **No Signature**: Any program/module meets the requirement.
   - **Any Signature (Unknown Root)**: Programs/modules with a digital signature will meet the requirement, but the certificate's root issuer does not need to be trusted by the operating system.
   - **User Signature + Microsoft-Trusted Signature (Code Root)**: If the program/module has a digital signature trusted by `ci.dll` (unaffected by the user-mode "Trusted Root Certification Authorities" store) or has a User Signature, it meets the requirement.
   - **User Signature + Microsoft/Antivirus Signature**: If the program/module has a digital signature certificate directly issued by Microsoft, or one trusted by a Microsoft-recognized antivirus software, or has a User Signature, it meets the requirement.
   - **User Signature Only**: If the program/module has a digital signature of User Signature, it meets the requirement.
 - **Image Load Protection**: When checked, if an application within the enclave attempts to explicitly load any module, and the module does not meet the requirements, its loading will be blocked.

The Process Creation Handling consists of the following configurations:
 - **When Trusted**: If a child process created by the initiating process meets the signature requirements, the following actions are possible:
   - **Allow Execution**: Continue execution within the enclave.
   - **Block Execution**: Prevent execution both inside and outside the enclave.
   - **Eject**: Kick it out of the enclave scope, removing its protection from the enclave.
 - **When Untrusted**: If a child process created by the initiating process does not meet the signature requirements, the following actions are possible:
   - **Allow Execution**: Continue execution within the enclave.
   - **Block Execution**: Prevent execution both inside and outside the enclave.
   - **Eject**: Kick it out of the enclave scope, removing its protection from the enclave.

The Other Options consist of the following configurations:
 - **UIPI Level**: The level for processes running under a standard user account is typically "Medium", while elevated processes usually have "Medium+" or "High". Programs with a level lower than the selected level will be unable to simulate user actions on windows of processes running within the enclave via window messages, or to obtain window information using methods other than screenshot capture.
 - **Prevent Terminate**: Prevent processes running within the enclave from being terminated.
 - **Allow Debuging**: Allow processes within the enclave to be debugged. This is an extremely insecure behavior, as it will allow any elevated process to fully access any information of processes within the enclave, including stored user passwords. Although in the beta phase, MajorPrivacy adopted this configuration for itself to facilitate debugging, users should absolutely not use this option during normal use.

Unless the “Allow Debuging” option is enabled, MajorPrivacy will prevent processes running within the enclave from being accessed with intrusive permissions (such as reading memory) by any process outside the enclave (except PPL processes).