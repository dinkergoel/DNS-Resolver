# DNS-Resolver
This project is to implement a DNS resovler of a hostname and understand the working of DNS in Network space. Below is the detailed description of the requirement:

1. Almost everything on the Internet involves DNS resolution. If DNS is slow, the
performance of your application is going to suffer. The goal of this homework is write
your own DNS resolver, and compare its performance with other existing DNS resolvers.
You get to write your own “dig” tool and a “DNSSEC” resolver.

2. You will be implementing a DNS resolver. In response to an input query, the resolver will
first contact the root server, then the top-level domains, all the way down to the
corresponding name server to resolve the DNS query.

a. You can access the IP address of the root servers from
https://www.iana.org/domains/root/servers. Your server program must use this
list to find a working root server. When the request to the root is not answered,
your code should move on to the next server in the list.

b. Build a dig-like tool called “mydig”. The mydig tool takes as input: (1) name of the
domain you want to resolve and (2) type of DNS resolution. The type represents
the DNS query type. Your tool should work for the following types: “A”, “NS”,
“MX”.
When run as “./mydig <name> <type>”, your tool should display the results
“similar” to the results from the dig tool (the additional section is not needed, just
the resolved IP address).
The output should be of the following form
./mydig www.cnn.com A
QUESTION SECTION:
 www.cnn.com. IN A

 ANSWER SECTION:
 www.cnn.com. IN A 151.101.209.67

 Query time: 24 msec
 WHEN: Fri Feb 2 10:26:27 2018 
 MSG SIZE rcvd: 84

3. A similar output is expected for MX and NS records. In some cases, when using MX
and NS records, the dig tool returns the answers in the “Authority” section instead
of Answer section. It is ok to return the authority section results in that case.
3. In some cases, you may need additional resolution. For example, google.co.jp will
often not resolve to an IP address in one pass. Your tool should handle such cases

DNSSEC explanation: https://www.cloudflare.com/en-gb/dns/dnssec/how-dnssec-works/
