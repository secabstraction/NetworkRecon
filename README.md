# NetworkRecon #

NetworkRecon is a PowerShell script consisting of three functions that allow you to perform analysis of observable network protocols for vulnerabilities. The functions included in this script are Invoke-NeighborCacheAnalysis, Invoke-TraceCollect, and Invoke-LiveAnalysis.

Invoke-NeighborCacheAnalysis - Looks for the presence of Layer 2 multicast addresses of potentially vulnerable protocols in the system ARP cache.
Invoke-TraceCollect - Performs a time-limited network trace in either .etl or .cap format depending on supported operating system features.
Invoke-LiveAnalysis - Uses a raw IP socket to listen to and parse potentially vulnerable protocols and expose details.

These three functions can be used by red team members to determine whether the network can be attacked through attacks like route manipulation, man-in-the-middle attacks, VLAN hopping, and network boot attacks. They can also be used by blue teamers to identify where potentially attackable protocols are visibile within a network environment.

## Quick Start Guide ##

Open an administrative PowerShell terminal from the Windows command line with 'powershell.exe -exec bypass'

Type 'Import-Module NetworkRecon.ps1'.

Each of the three PowerShell functions can be run without supplying any of the optional arguments to assess the posture of the network. Optional arguments allow the user control the information displayed, location where output should be stored, and runtime for packet capture.

A full writeup on this script can be found at: https://www.giac.org/paper/gcih/18544/identifying-vulnerable-network-protocols-powershell/119997

### Credits ###

The Invoke-LiveAnalysis function borrows the basic raw socket packet sniffer code used in Inveigh.ps1 at https://github.com/Kevin-Robertson/Inveigh.