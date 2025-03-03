# DNS






# DNS Records
- A Domain Name System Record is a set of instructions used to connect domain names with internet protocol (IP) addresses within DNS servers. DNS makes it possible for users to browse the internet with customizable domain names and URLs rather than complex numerical IP addresses.
- This function—translating human-readable domain names into machine-readable IP addresses—is the reason that DNS is often referred to as "the phonebook of the internet." DNS records are a vital part making this process fast and secure for internet users.
- DNS records are simple text files called "zone files" that give instructions on how to handle DNS requests. When you type a website address into your browser, a DNS query is created. This query is sent to multiple DNS servers, which use DNS records to find the correct IP address and connect you to the website. These records are stored on special DNS servers called authoritative nameservers. They also include a setting called "time-to-live" (TTL), which tells how long the information is considered valid before being updated.
- Commonly used DNS records include: A and AAAA records, CNAME, DNAME and ALIAS records, CAA records, CERT records, MX records, SOA records, NS records, PTR records, SPF records, SRV records and TXT records. Each of these records has a unique function and understanding each is an important part of a functioning DNS system.

## Common types of DNS Records
DNS management relies on the interconnectedness of DNS servers. Knowing how your DNS servers interact with each other through DNS records will make managing your DNS a less daunting task.

<details>
  <summary> Click to view Detailed information on the common types of DNS records</summary>

### A records
- Address records, or A records, are the most common DNS records used. They create a direct connection between an IPv4 address and a domain name. IPv4 addresses have the following format: 93.184.216.34.
---

### AAAA records
- Like A records, this type of record connects domain names to IPv6 addresses. IPv6 addresses have more numerals than IPv4 address and are becoming more common as options for IPv4 addresses are running out.
---

### CNAME records
- Canonical name records, or CNAME records, direct an alias domain to a canonical domain. This means that this type of record is used to link subdomains to domain A or AAAA records.
- For example, instead of creating two A records for www.example.com and product.example.com, you could link product.example.com to a CNAME record that is then linked to an A record for example.com. The value is that if the IP address changes for the root domain, only the A record will have to be updated and the CNAME will update accordingly.
---

### DNAME records
- Delegation name records, or DNAME records, are used to redirect multiple subdomains with one record and point them to another domain.
- For example, a DNAME record linking domain.com to example.com will link product.domain.com, trial.domain.com, and blog.domain.com to example.com. These records are helpful in managing largescale domains and in managing domain name changes by ensuring subdomains are properly linked.
---

### CAA records
- Certification authority authorization records, or CAA records, allow domain owners to specify which certificate authorities (CAs) can issue certificates for their domain. A CA is an organization that validates the identity of websites and connects them to cryptographic keys by issuing digital certificates.
---

### CERT records
- Certificate, or CERT records, store certificates that verify the authenticity of all parties involved. This type of record is particularly valuable when securing and encrypting sensitive information.
---

### MX records
- Mail exchange, or MX records, direct emails to your domain mail server. These records, along with an email server, allow for the creation of individual email accounts, such as user@example.com, that are linked to the domain (example.com).

### NS records
- Nameserver, or NS records, show which DNS server is acting as the authoritative nameserver for your domain. Authoritative nameservers contain the final information about a specific domain and its corresponding IP address. An NS record points to all of the different records your domain holds. Without NS records, users will not be able to access your website.

### SOA records
- Start of authority, or SOA records, store important administrative information about a domain. This information can include the domain administrator’s email address, information on domain updates and when a server should refresh its information.
---

### PTR records
- Pointer records, or PTR records, work in the opposite direction of A records. They are used to connect an IP address with a domain name, instead of a domain name with an IP address. When a DNS lookup begins with an IP address, it then finds the corresponding hostname. These records are used to detect spam by checking if the IP addresses and associated email addresses are used by legitimate email servers. PTR records must be set up by the server host.
---

### SPF records
- Sender policy framework, or SPF records, are used to identify the mail servers that can send emails through your domain. This helps prevent your domain from being used by spammers or for malicious purposes by letting email receivers know that what they are receiving has been authorized.
---

### SRV records
- Service, or SRV records, identify a host and port for specific services, such as messaging, for a domain. Ports are virtual connection points that allow digital devices to separate different types of traffic.
---

### ALIAS record
- ALIAS records are used to direct your domain name to a host name and not an IP address. For instance, if your domain name is example.com, you can point it to product.differentexample.com using an ALIAS record.
---

### NSEC records
- Next secure records, or NSEC records, allow for proof of non-existence. This means that these records exist to confirm that other records do not exist. Being able to confirm the non-existance of a record saves time when searching for specific records.
---

### URLFWD records
- URL forwarding (or URL redirecting) is a technique used to make a single web page available via multiple URLs. NS1 Connect users can easily set up URL forwarding (HTTP redirects or masking) between zones. There are three types of URL redirects: Permanent (301), temporary (302), or masking.
---

### TXT records
- Text, or TXT records, store textual information related to domains and subdomains. Text records allow for the storage of SPF records and email verification records. DKIM and DMARC records, which are stored in TXT records, help email servers confirm that a message is coming from a reliable source.
---

</details>

- Overview of most common types of DNS records are:

| **Record Type**      | **Abbreviation**           | **Functionality**                                                                                                                                                 | **Example**                                                                                                  |
|----------------------|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| **A Record**         | **Address Record**          | Connects a domain name to an IPv4 address.                                                                                                                          | `example.com` → `93.184.216.34`                                                                               |
| **AAAA Record**      | **IPv6 Address Record**     | Connects a domain name to an IPv6 address.                                                                                                                         | `example.com` → `2001:0db8:85a3:0000:0000:8a2e:0370:7334`                                                   |
| **CNAME Record**     | **Canonical Name Record**   | Links an alias domain to a canonical domain, often used for subdomains.                                                                                           | `www.example.com` → `example.com` (so if the IP of `example.com` changes, `www.example.com` is updated)       |
| **DNAME Record**     | **Delegation Name Record**  | Redirects multiple subdomains to another domain. Useful for managing large-scale domain changes.                                                                  | `domain.com` → `example.com` (redirects `product.domain.com`, `trial.domain.com` to `example.com`)             |
| **CAA Record**       | **Certification Authority Authorization Record** | Specifies which certificate authorities can issue SSL/TLS certificates for the domain.                                                                            | `example.com` → Allows `Let’s Encrypt` and `DigiCert` as certificate authorities                             |
| **CERT Record**      | **Certificate Record**      | Stores certificates to verify the authenticity of parties involved, mainly for secure and encrypted communication.                                                 | `example.com` → Certificate data for authenticating communications                                          |
| **MX Record**        | **Mail Exchange Record**    | Directs emails to the mail server for a domain, allowing email creation like `user@example.com`.                                                                  | `example.com` → `mail.example.com`                                                                            |
| **NS Record**        | **Name Server Record**      | Specifies the authoritative nameservers for a domain, pointing to servers that store all domain records.                                                         | `example.com` → `ns1.exampledns.com`, `ns2.exampledns.com`                                                   |
| **SOA Record**       | **Start of Authority Record** | Stores domain administrative info like the admin’s email and domain update information.                                                                          | `example.com` → Admin Email: `admin@example.com`, Refresh Time: `86400 seconds`                              |
| **PTR Record**       | **Pointer Record**          | Links an IP address to a domain name (reverse of A record). Often used for spam filtering and validating email servers.                                          | `93.184.216.34` → `example.com`                                                                               |
| **SPF Record**       | **Sender Policy Framework Record** | Identifies which mail servers are authorized to send emails for a domain, helping to prevent spam or email spoofing.                                               | `example.com` → `v=spf1 ip4:93.184.216.34 -all`                                                             |
| **SRV Record**       | **Service Record**          | Defines the host and port for specific services like messaging or VoIP on a domain.                                                                              | `_sip._tcp.example.com` → `sipserver.example.com:5060`                                                      |
| **ALIAS Record**     | **Alias Record**            | Directs a domain to a hostname (instead of an IP address).                                                                                                        | `example.com` → `product.differentexample.com`                                                               |
| **NSEC Record**      | **Next Secure Record**      | Confirms the non-existence of a record, useful for security and DNS lookup efficiency.                                                                            | `example.com` → Confirms that no DNSSEC record exists for `example.com`                                       |
| **URLFWD Record**    | **URL Forwarding Record**   | Redirects users to a different URL when they visit a particular domain, useful for forwarding or masking URLs.                                                     | `example.com` → Redirects to `www.example.com` (with options for permanent or temporary redirects)            |
| **TXT Record**       | **Text Record**             | Stores textual information, such as SPF, DKIM, and DMARC records, to verify email authenticity and security.                                                     | `example.com` → `v=spf1 include:_spf.google.com ~all` (for email verification)                               |

### Key Points:
- **A and AAAA Records** link domain names to IP addresses (IPv4 and IPv6, respectively).
- **CNAME Records** help create easier management of subdomains by pointing them to a canonical domain.
- **DNAME Records** allow for the redirection of multiple subdomains with one record.
- **MX Records** are essential for directing email traffic to the correct server.
- **SPF Records** help verify that only authorized servers can send emails on behalf of your domain.
- **SRV Records** are used for specifying services (like messaging or VoIP) associated with a domain.
- **TXT Records** store text-based information for security purposes, such as email verification and spam prevention.

This version should match your requested abbreviation format and keep everything clear and simple.
