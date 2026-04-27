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

* Detected multiple failed login attempts within a short time window  
* Repeated login attempts from a single IP address  
* Pattern suggests automated attack behaviour  

## Conclusion

This activity suggests a potential brute-force attack.

## Mitigation

* Block IP address
* Enable account lockout policies
* Use multi-factor authentication
  
## Analyst Insight
The repeated login attempts from a single IP within a short period indicates a likely brute-force attack. This type of behaviour is commonly associated with automated scripts attempting to guess credentials.

If observed in a real SOC environment, this would trigger an alert for suspicious authentication activity.
