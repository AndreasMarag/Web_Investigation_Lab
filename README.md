# Web_Investigation_Lab

To solve this lab, you must know what percent-encoding is.
Percent-encoding is a method to encode arbitrary data in a uniform resource identifier (URI) using only the US-ASCII characters legal within a URI.
For more info, visit Wikipedia's website (https://en.wikipedia.org/wiki/Percent-encoding).


Q1

By knowing the attacker's IP, we can analyze all logs and actions related to that IP and determine the extent of the attack, the duration of the attack, and the techniques used. 
Can you provide the attacker's IP?

Answer

To solve this question, you download the lab file first, and then open the file with Wireshark.
In Wireshark, first, you look at the HTTP protocol for any suspicious behavior. You can easily spot that
the IP 111.224.250.131 is doing an SQL injection attack on our server.


Q2  

If the geographical origin of an IP address is known to be from a region that has no business or expected traffic with our network, 
this can be an indicator of a targeted attack. Can you determine the origin city of the attacker?

Answer

To solve this problem, you can simply type the IP address from Q1 into this website https://whatismyipaddress.com/ip-lookup.
You will find that the city of the attacker is Shijiazhuang.

Q3

Identifying the exploited script allows security teams to understand exactly which vulnerability was used in the attack. 
This knowledge is critical for finding the appropriate patch or workaround to close the security gap and prevent future exploitation.
Can you provide the vulnerable PHP script name?

Answer

The attacker is taking advantage of a vulnerable PHP script to launch his SQL injection attack. We analyze the file in Wireshark,
and we can spot that the attacker is using the search.php script to launch his attack.

Q4

Establishing the timeline of an attack, starting from the initial exploitation attempt, 
what is the complete request URI of the first SQLi attempt by the attack

Answer

To solve this question, you simply go to Wireshark and find the first successful HTTP request that the attacker made using the vulnerable PHP script.
The URI is "/search.php?search=book and 1=1; -- -". As we can see, the attacker is using search.php to launch a SQL injection attack, and the server,
returns "200 OK " which means that the request was valid.

Q5

Can you provide the complete request URI that was used to read the web server's available databases?

Answer









