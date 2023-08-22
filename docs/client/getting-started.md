---
sidebar_position: 1
---

# Getting started

## Install

Install via Nuget:

TODO

## Use the client

### HTTP DNS client

```csharp
var httpDnsClient = new HttpsDnsClient(new Uri("https://cloudflare-dns.com/dns-query"));

var question = new Question(new DomainName("www.google.de"), Type.A, Class.In);
Message message = await httpDnsClient.ResolveAsync(question);

ResourceRecord resourceRecord = message.Answers[0];
if (resourceRecord.Class == Class.In && resourceRecord.Type == Type.A)
{
    Console.WriteLine("IP: " + ((AResourceData)resourceRecord.ResourceData!).Address);
}
```

### UDP DNS client

```csharp
var udpDnsClient = new UdpDnsClient(IPAddress.Parse("1.1.1.1"));

var question = new Question(new DomainName("www.google.de"), Type.A, Class.In);
Message message = await udpDnsClient.ResolveAsync(question);

ResourceRecord resourceRecord = message.Answers[0];
if (resourceRecord.Class == Class.In && resourceRecord.Type == Type.A)
{
    Console.WriteLine("IP: " + ((AResourceData)resourceRecord.ResourceData!).Address);
}
```
