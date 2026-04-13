# Offensive Security Capstone: Complete Audit & Execution Log
**Candidate:** Thulile Masuku  
**Date:** April 2026  
**System ID Verified:** 234933  

---

## 1. SUCCESSFUL EXECUTION PATH
*The following commands successfully extracted the required system data.*

### A. Hardware Identification
```bash
# Navigating to the kernel's hardware identification directory
cd /sys/class/dmi/id/

# Extracting the unique Board Identifier
cat board_name
# RESULT: 234933

Web Server Status
Bash

# Verifying the target Nginx service was operational
service nginx status
# RESULT: Active (running)

TROUBLESHOOTING: "EMPTY" RESULTS & SEARCHES

The following commands were part of the audit process but returned no data (null), confirming environment isolation.
A. Host-Level Search for Lab Files
Bash

# Searching the Kali host for files that existed only in the lab container
find ~ -maxdepth 2 -name "*capstone*"
# RESULT: (Empty/Nothing returned)

irectory Audit
Bash

# Checking for project-specific directories in the root home folder
ls -la | grep "alx"
# RESULT: (No matching lines found)

TECHNICAL ERRORS & FAILURES

Documenting the 'Fatal' errors encountered during the deployment phase.
A. Git State Error

    Command: git push origin main

    Error: fatal: updating an unborn branch with changes added to the index

    Cause: Attempting to update a branch before the initial commit was registered.

    Resolution: Force-reset the Git directory using rm -rf .git and git init.

B. Remote Push Refusal

    Command: git push -u origin main

    Error: error: failed to push some refs to [URL]

    Cause: Divergence between local and remote repository history.

    Resolution: Used git push -f to synchronize the final as-built documentation.

GITHUB HURDLES & AUTHENTICATION

Summary of the security obstacles faced while connecting to the remote repository.

During the final submission phase, standard Password Authentication was denied by GitHub's security protocol (Support for password authentication was removed).

Resolution Strategy:

    Shifted from the root terminal to the User Shell for consistent permissions.

    Generated a GitHub Personal Access Token (Classic).

    Updated scopes to include full repo control.

    Authenticated successfully using the token as a secure password bypass.========
