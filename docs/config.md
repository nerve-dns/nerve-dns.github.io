---
sidebar_position: 2
---

# Config

The config is a json file named "nerve.json" in the same directory the executable is.

## Quick example

Here is an example of a "nerve.json" config file:

```json
{
    "Nerve": {
        "Ip": "0.0.0.0",
        "Port": 5333,
        "ForwarderMode": "https",
        "Forwarders": [
            "https://cloudflare-dns.com/dns-query"
        ],
        "Blocklists": [
            {
                "Ip": "0.0.0.0",
                "Lists": [
                    "C:\\Some\\Path\\my_blocklist.txt",
                    "https://example.com/domains.txt"
                ]
            }
        ]
    },
    "Logging": {
        "LogLevel": {
            "Default": "Debug",
            "System": "Warning",
            "Microsoft": "Warning"
        },
        "Console": {
            "LogLevel": {
                "Default": "Debug",
                "System": "Warning",
                "Microsoft": "Warning"
            }
        }
    }
}
```

## Detailed explanation

| Key | Default  | Description  |
|:---|:---:|---|
| Ip | "127.0.0.1"  | The IP address where nerve binds to. |
| Port | 53 | The port where nerve binds to.  |
| ForwarderMode | "https" | In which forwarder mode to run ("https" = DNS over HTTPS, "udp" = DNS over UDP). |
| Forwarders | ["https://cloudflare-dns.com/dns-query"] | An array of the IPs ("udp" mode) or URIs ("https" mode). |
| Blocklists | [] | An array of blocklist objects containing the IP and an array of blocklist file paths or urls. |
