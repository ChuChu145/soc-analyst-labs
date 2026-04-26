# Linux Failed Login Investigation

## Objective

Identify suspicious login attempts on a Linux system.

## Tools Used

* Linux
* journalctl
* grep

## Steps Taken

1. Checked authentication logs
2. Filtered failed login attempts
3. Identified repeated IP address

## Findings

* Multiple failed login attempts detected
* Same IP repeatedly attempting access

## Conclusion

This activity suggests a potential brute-force attack.

## Mitigation

* Block IP address
* Enable account lockout policies
* Use multi-factor authentication
