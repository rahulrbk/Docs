# Day One Task

   ## DNS records
   ## Linux cli
   ## Websites:
 1. census.io
    * it is used for subdomain enumuration of an organisation.
 * scanning list
 > HTTP
 > HTTPS
 > POP3, IMAP, SMTP, SMTPS
 > SSH
 > Telnet
 > Modbus, S7, BACNET, DNP3, Tridium Fox etc.
 2. Shodan.io
 * It is a search engine.
   * Shodan collects data mostly on web servers (HTTP/HTTPS – ports 80, 8080, 443, 8443), 
   * FTP (port 21), SSH (port 22), Telnet (port 23), SNMP (port 161), IMAP (ports 143, or (encrypted) 993), SMTP (port 25), SIP (port 5060),and Real Time Streaming Protocol (RTSP, port 554). The latter can be used to access webcams and their video stream.
 3. Hunter.io
    * search for email address of the company or an organisation.
 4. spiderfoot
   - SpiderFoot can be used offensively  for reconnaissance of your target or defensively to gather information about what you or your organisation might have exposed over the Internet.
     - You can target the following entities in a SpiderFoot scan:

       * IP address
       * Domain/sub-domain name
       * Hostname
       * Network subnet (CIDR)
       * ASN
       * E-mail address
       * Phone number
       * Username
       * Person's name

 # Tools
 1. amass tool
 >types 
 - amass intel:
   - $amass intel -d owasp.org -whois :reverse look up of dns.
   - $amass intel -org owasp.org :used to find ASN of the domain.
   - $amass intel -asn  22222 -ip :used to fetch parent root domains 
   - 
 - amass enum:
    > Scan types
    - active:Using Amass in active configuration mode means that you will have more accurate results and more assets may be discovered
       * '$ amass enum -active -d owasp.org -public-dns -brute -w /root/dns_lists/deepmagic.com-top50kprefixes.txt -src -ip -dir amass4owasp -config /root/amass/config.ini -o amass_results_owasp.txt' 
          - performs subdomain brute-forcing in multiple ways (wordlist, masks, etc.) along with the “-active” flag being enabled
      
    - passive
      - $amass enum -passive -d owasp.org -src:is used to searching for subdomains on owasp.org while asking Amass to display the data sources where it found each subdomain.
 - amass track:
    -compare results across enumerations performed against the same target and domains.
       - $ amass track  -config /root/amass/config.ini -dir amass4owasp -d owasp.org -last 2
 - amass db:
    - $ amass db -dir amass4owasp -list: list all the different enumerations you have performed in terms of the given domains and are stored in the “amass4owasp” graph database.
    - $ amass db -dir amass4owasp -d owasp.org -enum 1 -show: retrieve the assets identified during that enumeration 
 
  
 ---
  2. NMAP tool
  >It is used to scan open ports in a network or outside a network.
  >also used to show the version of the software used inside the network.
  ---
  3. Aquatone tool
  >Aquatone is a tool for visual inspection of websites across a large amount of hosts and is convenient for quickly gaining an overview of HTTP-based attack surface.
  ---
  4. Sublist3r
  >Sublist3r is a python tool designed to enumerate subdomains of websites using OSINT. It helps penetration testers and bug hunters collect and gather subdomains for the domain they are targeting. Sublist3r enumerates subdomains using many search engines such as Google, Yahoo, Bing, Baidu and Ask. Sublist3r also enumerates subdomains using Netcraft, Virustotal, ThreatCrowd, DNSdumpster and ReverseDNS.
  ---
  5. gobuster
    Gobuster is a tool used to brute-force:

      - URIs (directories and files) in web sites.
      - DNS subdomains (with wildcard support).
      - Virtual Host names on target web servers.
  ---

   
