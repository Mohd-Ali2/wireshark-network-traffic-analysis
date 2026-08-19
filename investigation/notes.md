# Investigation Notes

## Victim

- IP: 10.0.19.14
- MAC: 00:60:52:b7:33:0f
- Hostname: DESKTOP-5QS3D5D
- Domain: mshome.net
- Username: Patrick.zimmerman

## Initial Findings

The host 10.0.19.14 generated the majority of the traffic in the capture and was selected for further investigation.

At 03:24:43.660908, the host queried the internal DNS server 10.0.19.9 for `bupdater.com`.

At 03:24:43.825443, the DNS server returned `23.227.198.203`.

At 03:24:43.831670, the host started a TCP connection to `23.227.198.203` on port 757.

This sequence shows a DNS lookup followed immediately by a connection to the resolved IP.
