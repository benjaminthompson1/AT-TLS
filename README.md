# AT-TLS z/OS Configuration

Configuration members for AT-TLS (Application-Transparent Transport Layer Security) on z/OS, implementing secure communications for TN3270 and JCL Expert server.

## Components

### Policy Agent Files
- `pagent.conf` - Main Policy Agent configuration
- `pagent.TCPIP.conf` - TCP/IP stack configuration
- `pagent.TTLS.policy` - AT-TLS rules for TN3270 (port 2023) and JCL Expert server (port 8100)

### TN3270 Configuration
- `PORT2023` - TN3270 server settings for secure port
- `TN3270` - Global TN3270 server parameters

### Started Task
- `PAGENT` - Policy Agent JCL procedure

## Security Features
- TLS 1.2/1.3 enabled for TN3270
- TLS 1.2 only for JCL Expert
- Older protocols (SSLv2, SSLv3, TLSv1.0, TLSv1.1) disabled
- Client authentication required for JCL Expert server

## Required Keyrings
- TN3270: TCPIP/TN3270.TTLS
- JCL Expert Server: CXPSRV/CXPServerRing
- JCL Expert Client: IBMUSER/CXPClientRing

