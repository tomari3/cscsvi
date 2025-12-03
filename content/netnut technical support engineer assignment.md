# Netnut Support Engineer Assignment

## Part A - Log Analysis

1. 2025-01-12 18:42:10 country=US status=200 latency=312ms
2. 2025-01-12 18:42:12 country=DE status=200 latency=120ms
3. 2025-01-12 18:42:15 country=DE status=503 latency=-
4. 2025-01-12 18:42:20 country=BR status=200 latency=210ms
5. 2025-01-12 18:42:25 country=DE status=200 latency=700ms
6. 2025-01-12 18:42:30 country=DE status=502 latency=-
7. 2025-01-12 18:42:36 country=IN status=504 latency=-
8. 2025-01-12 18:42:44 country=IN status=200 latency=1500ms

### Observation
- **normal lines:** Lines 1,2,4 look normal.
- **abnormal lines:** Lines 3,5,6,7 look abnormal
	- line 3: service unavailable
	- line 5: latency 700
	- line 6: bad gateway
	- line 7: gateway timeout
	- line 8: latency 1500
- **noticeable patterns:**
	- **Server side:** all problems are 500s (serverside)
	- **Problem locality/origin:** lines 3,5,6 are from DE, lines 7,8 are from IN. 
	- **Problem timeline:** problems start at line 3 and seems to end\decaying at line 8
	- **flickering:** there are flickers of 200s with high latency between server errors
### Possible Explanations
1. server overload
2. breaking changes
### Immediate Checks
- Server status
- abnormal events in said regions (Huge cricket game in India for example)
### Communication
- **To My Manager:** Starting at 2025-01-12 18:42:15 there have been several on and off 500s followed by slow latency. The incident spanned over 34 seconds. possibly isolated to DE and IN.
- **To The Costumer:** Dear Customer, we have identified connection issues in the following regions: DE, IN. Service now works normally. We are investigating the causes and will improve upon them to mitigate such incidents in the future. 

## Part B - Customer Case

A customer in Germany says:
- Their success rate (successful requests out of total requests) dropped from 92% to 54%
overnight
- It only happens during working hours (09:00–18:00 CET)
- Other countries are fine
### Questions
- Have there been ANY changes in their workflow since yesterday? 
- What sites are you trying to access? It might not be a proxy problem
- Could I get some logs data, hopefully containing both success and failures? 
- Is there a volume difference between working hours and other hours?
### Possibilities
- The wanted site might detected and blocked our proxy
- It might be the country's ISP peak hours traffic causing failed requests
### Priorities (from TOP to LOW)
1. All requests are failing: total failure is unacceptable for a paying customer, causing massive dissatisfaction, it should be acknowledged and fixed immediately.
2. 92% to 54% (38%) Dropped success rate (Germany customer): A drop this big is service breaking and could not be ignores. 
3. VIP customer: While VIPs deserve service, a drop of 5% is not breaking. It should be addressed and fixed but it is not as taxing on the product as the other problems are. 
4. Brazil: the term "slow" is subjective and illegible, I would request more data and check if their statement holds ground.
### If Unsolved
A break this big could do a lot of damage.  They could lose important time sensitive data and fail to deliver on their product. Imagine Instagram or the Moovit rejecting half of your requests, how long would it take you to switch an app? The company could loss customers money and or trust.
## Part C: Research & Learning
### What is a 503?
A 503 means Service Unavailable, meaning the server tells the client that it is down and can not handle the request. It would be like ordering Wolt pizza and getting back a call telling you they can not take your order. It usually happens if there is an excessive rush hour, maintenance or a crash. 
### What is IP Geolocation?
IP geolocation is estimating a geographic location based on an IP address. Like phone have a prefixed code based on area (+972 for Israel, 04 for north, etc) we can keep track of IP location and their owners which are usually ISPs. The problem is that sometimes countries and companies will sell or trade blocks of IP, and that these lists are not publicly available or maintained. So it is up to the company to keep score.
### What is Proxy Rotation?
Proxy rotation is a technique to switch IPs between requests, to remain undetected. 
Imagine your local coffee shop gives out a free cup of coffee to each customer. If you would like more than one cup you could come in as many times as you want in different clothes and costumes, as long as you are undetected. Each costume is an IP address. The problem is that if you change clothes every few minutes, it might be a problem to sit at the cafe for hours and closing your original tab. That is why we don't use proxy rotation in online checkouts.
## Pard D - Creativity & Initiative
Imagine you are the first Support Engineer in a new company. There are no tools, no dashboards, and no documentation.
A customer reports: “I can’t log in to my account. It was working fine yesterday.”
### Today's fixes (in no particular order)
1. I will log in to my account if the problem is client or server side
2. I would try to log in using their credentials to see if it works locally
3. I would guide them through a passwords reset to see if that might work
4. I would check their environment: operation system, web browser, VPN, extensions and so on and look for red flags
5. I would try the obvious on and off, reseting the computer, closing and opening browser, clearing cache and temp folders. 
6. If above does not work I might get suspicious and get advice from my team leader or try to gently verify the costumers identity
### Tomorrow's fixes: Tools
1. dashboard: gathering information from the "Today's fixes" section and more: client's last login, login locations, number of login attempts, account status, payment status. functionality like a quicker admin guided password reset process.
2. user logs: searchable logs with failure reason, timestamps. 
3. documentation page: FAQ style solutions for each frequent problem for quicker troubleshooting. I would also create a user friendly version and script it to prompt after a user's several failed logins. I would couple the support process with an "after support" form detailing the process from problem to solution, similar to CTF write-ups.
## Part E - Practical Task: Web Scraping
https://github.com/tomari3/ScrapeWrangler/tree/main/amazon_proj