# Secure Enclave
This document refers to the user interface panel "Secure Enclave". If you are looking for the concept "Secure Enclave", please see <a href="../Related Conception/Secure Enclave.md">Secure Enclave</a>.

In this panel, it is composed of three parts by default: Enclave Process Tree, Enclave Process Rules, and Process Details.

(1) Enclave Process Tree
The Enclave Process Tree takes the enclave as the "root" of the process tree, and all process items are derived from it. There can be multiple enclaves. When an enclave process starts, MP will automatically add it to the corresponding enclave in the Enclave Process Tree, and remove it when it terminates or is ejected from the enclave.
Note: The Enclave Process Tree is organized hierarchically based on enclave affiliation and process startup relationships. Each program item represents a strict instance.

(2) Process Rules
Here, rules related to "processes" are displayed. You can right-click in the blank area to bring up a context menu to perform the following operations: create rules, copy panel content. You can right-click on existing process rules to perform: enable/disable rules, delete rules, copy rules, edit rules, etc.
For details related to process rules, please refer to the document "Program Rule".

(3) Process Details

This section includes several sub-tabs.

{1} Includes "Loaded Module", which displays the module information loaded by the instance corresponding to the selected process in the Enclave Process Tree. Due to the logging-based implementation mechanism, it will include module loading information for terminated processes. If no process is selected in the Enclave Process Tree, or if the selected process has no recorded instances (which is almost impossible), it will display blank. When a process item with recorded information is selected, this section will display the recorded process instance items. Unlike "Running Process", each instance item can be expanded. When an instance item is expanded, it will display in indented form all modules that have attempted to be loaded into the relevant process (usually executable files and dynamic link libraries), and display relevant information. The "Trust Level" column identifies the issuer's trust level recognized by MP for the digital signature attached to the module (if any). The "LastStatus" column indicates whether the module was successfully loaded into the target instance the last time (usually referring to whether it was allowed to be loaded by MP, not whether it initialized successfully). The "Signing Certificate" displays the name of the certificate issuer.

{2} Includes "Execution Monitor", which monitors which processes the instance of the relevant program item has launched, and which processes have launched it.

{3} Includes "Entry Monitor", which monitors whether the instance of the relevant program item has attempted to access other processes, and whether other processes have attempted to access the relevant instance.

{4} Includes "Trace Log", where relevant logs will be displayed when users specifically set up to track the operations of a certain program item.

For the next panel see <a href="./Access Protection.md">"Access Protection"</a>.