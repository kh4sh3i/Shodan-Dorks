# Shodan Dorks
a curated list of shodan dorks for finding sensitive data in shodan.io


## 1️⃣ Search for secret API keys publicly exposed on websites :
ex : Searching for slack API token on all the scanned websites 
```
http.html:"xoxb-"
```

## 2️⃣ Search using 'favicon' hash :
- One of the most accurate way of finding services

ex- Find all jenkins server : 
```
http.favicon.hash:81586312
```

Tip: https://github.com/sansatart/scrapts/blob/master/shodan-favicon-hashes.csv



## 3️⃣ Search using website's title :

ex - Find all grafana dashboards
```
http.title:"Grafana"
```



## 4️⃣ Search services vulnerable to a particular CVE :

ex - Search all machines vulnerable to 'eternal blue'. 
```
vuln:ms17-010
```

Search a particular CVE :
ex - Services that are vulnerable to Heartbleed
```
vuln:CVE-2014-0160
```

Note:This is only available to users of higher API plan



## 5️⃣ Search for a particular port + service :

ex - SSH on port 22 or 3333  
You can use this to find services on non-standard port. 
```
Like : ssh -port:22
```
ssh which is not on port 22

```
ssh port:22,3333
proftpd port:21
ssh -port:22
```


## 6️⃣ Search for a particular OS :

e.g. Checking for vulnerable win 10 home version
```
os:"Windows 10 Home 19041"
```


## 7️⃣  Combine filters to generate more targeted results

e.g. All windows 7 machines in India
```
country:"IN" os:"windows 7"
```

## top Shodan dorks 

* Jenkins CI 
```
"X-Jenkins" "Set-Cookie: JSESSIONID" http.title:"Dashboard"
```

* Docker Private Registries
```
"Docker-Distribution-Api-Version: registry" "200 OK" -gitlab
```

* MongoDB mag_right 
```
"MongoDB Server Information" port:27017 -authentication
```

* FTP Servers with Anonymous Login 
```
"220" "230 Login successful." port:21
```

* Mongo Express Web GUI
```
"Set-Cookie: mongo-express=" "200 OK"
```

### references
* [Top 40 Shodan Dorks for Finding Sensitive IoT Data](https://securitytrails.com/blog/top-shodan-dorks)
* [Awesome Shodan Search Queries](https://github.com/jakejarvis/awesome-shodan-queries)

