# Cyber_TornadoWebService

***Overview of the project****

This tornadowebservice challange is a web application task where we need to find and exploit the vulnerabilities, get an unauthorized access and retrieve the flag.

Inject new credentials thru (CSRF) Cross-Site Request Forgery attack thru hosting the payload on the local system .

Log in with the injected credentials.

Access sensitive data like flags and create a new user from a protected endpoint.

**The Tools to solve this challange:**

Kali Linux

Html

Json

Burpsuite

Curl

**Methodology to perform this challange:**

List the accessible endpoints and retrieve and submit requests on Burp Suite:

/get_tornados

/update_tornado

/login

/stats

/report_tornado

**We Studied the endpoint behaviors using the tools such as:**

curl

Burp Suite

browser developer tools

**Planning the Exploit:**

Find the vulnerabilities to create the actionable exploit.

Vulnerability: (CSRF) Cross-Site Request Forgery

The bot is then tricked into executing the JavaScript on your hosted page and exploit the authenticated session.

Inject the malicious data into the application (ID-kittykat PW-kittykat).

Log in and access the protected endpoint.

**Tasks:**

Create the malicious payload(index.html) to fetch data from /get_tornados.

Update the machine details in /update_tornado with the injected credentials.

Host this payload as index.html on a local server or on NGROK Public server if you have the subscription.

**Hosting the exploit and exploiting the vulnerability:**

Get the status of the Ip Machine to know about it

curl -X GET "http://94.237.63.109:45919/stats"

Run the following command to host index.html file http server.

python -m http.server 1337

Reporting a Tornado on the Box server.

curl "http://94.237.59.207:47563/report_tornado?ip=127.0.0.1"

Inject the new User to the server for getting access and store cookie data

curl -X POST "http://94.237.59.207:47563/login" \            -H "Content-Type: application/json" \ -d '{"username": "kittykat", "password": "kittykat"}' \ -c cookie.txt 

we have run the following command to get the cookie data.

curl -X GET "http://94.237.59.207:47563/stats" -b cookie.txt

Finally we have Submitted the retrived flag.

**Pictures:**

![pic1](https://github.com/user-attachments/assets/1b103e9a-cc89-4c9a-a5c0-81341ec3f3f3)

![pic2](https://github.com/user-attachments/assets/c6ac2174-f7b1-47dc-9d0a-cc03f77047b2)

![pic3](https://github.com/user-attachments/assets/30e4f880-68e9-4325-a715-cdf07484c2ef)
