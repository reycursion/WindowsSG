## Table of Contents 
1. LDAP
2. Active Directory
3. Commands CLI & PowerShell

### 1. LDAP

**LDAP (Lightweight Directory Access Protocol)** is a software protocol designed for accessing and managing directory services over a network.

LDAP Ports
* **Port 389**: This is the default port for non-secure LDAP communication, typically used for unencrypted LDAP traffic.
* **Port 636**: This port is used for Secure LDAP (LDAPS), which encrypts traffic using SSL/TLS, providing an additional layer of security when transmitting sensitive information, such as passwords.
The Naming Model explains how entries are organized and identified within the LDAP directory. Entries are arranged in a hierarchical, tree-like structure known as the **Directory Information Tree (DIT)**. This tree allows for logical grouping and identification of objects.

Each entry in the DIT is uniquely identified by a Distinguished Name (DN), which is a string that uniquely identifies an object within the directory.

Two Types of Names in LDAP:

* Distinguished Name (DN)
  *   Full path of an object within the LDAP directory.
  *   Includes Relative Distinguished Name (RDN) + Directory Location.
  *   Example: CN=Peter Parker, OU=S6, DC=army, DC=com
* Relative Distinguished Name (RDN)
  *   Unique identifier at each directory level.
  *   Does not include full directory structure.
  *   Example: OU=S6
 

### 2. Active Directory

### 3. Commands 


#### CLI 


#### PowerShell
