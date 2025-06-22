# Program Rules

Program Rules are an important component of the rules in MajorPrivacy. You can create them in the "Process Security" and "Secure Enclave" panels.

Typically, a program rule is applied to a program item, which can be an instance of an image file, a group of processes, or even all processes.

Users can set the "Enclave" option for a rule. Once set, the rule will only be effective within the corresponding scope. Usually, for the same program item, the priority of rules within an enclave is always higher than that of global rules.

The Behavior (Action) option can have the following values:

(1) **Allow**
   If a program item is blocked from running globally, this rule can be used within an enclave to allow its operation within that enclave. It can also be used globally.
   
(2) **Block**
   The selected program item will be unable to run within the scope of the rule (either globally or within a specific enclave).
   
(3) **Protect**
   Forces instances of specific program items to automatically join the corresponding enclave upon startup and be protected by it. A corresponding enclave must be set for such rules and they cannot be used globally. The protection level depends on the enclave's configuration. The enclave will still verify the trust level of processes matching this rule to decide whether to trigger an eject.
   
(4) **Audit**
   The behavior of programs hitting this rule will be logged in detail.
