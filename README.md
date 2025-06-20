# MajorPrivacy-Docs

<p align='center'>
EN | <a href='./README_zh-CN.md'>中文</a>
</p>

This is the Documentation of HIPS [MajorPrivacy](https://github.com/xanasoft/MajorPrivacy)

Major Privacy is an advanced privacy tool for Windows. It is a continuation of the PrivateWin10 project. It brings a multitude of new functionality made possible through the use of a custom kernel isolation driver. Conceptually, Major Privacy is a HIPS (Host Intrusion Prevention System). The driver can monitor and filter file/registry access as well as protect processes from being manipulated by other processes. It leverages the Windows built-in mechanisms to restrict network traffic, and brings a convenient collection of privacy-enhancing tweaks. It implements its own rule-based software restriction mechanism, i.e. the ability to prevent unauthorized or undesired applications from running. Using the process protection feature of the KernelIsolator driver, Major Privacy can protect unprivileged user processes from being compromised and their secrets exfiltrated, even from threads running with system or administrative privileges. Its ability to protect processes, in combination with its ability to restrict access to files and folders, helps to protect personal data. Furthermore, Major Privacy is capable of creating protected volumes located in encrypted container files, such that access to confidential data is only possible when the user provides the correct password and the tool is actively filtering filesystem accesses. The privacy agent logs file, registry, and network access, and provides comprehensive logs and visualizations of process activity on the host system. This enables the user to check if their applications are only doing what they want them to do. Major Privacy is designed to not only provide a line of defense against regular malware, but also to defend the user from legitimate - but overreaching - software, so that the software can be safely used and the companies behind it won't be able to access anything the user did not choose to make available.

Here you will be able to know more about Major Privacy.
If you want to develop a rule pack specifically for older versions of MajorPrivacy (not recommended), please check the rules for the corresponding version according to the Tag. Documents does not guarantee backward compatibility.
