
## Info
- Video: https://www.scaler.com/academy/mentee-dashboard/class/211440
- [HLD curriculum and readings](https://docs.google.com/spreadsheets/d/1dxNzZT_3dnkLESAj5T-GCm1pFFPeU_GWNAyr7m2gJsY/edit#gid=0)
- [LB reading](https://docs.google.com/document/d/1JYyRLK-frGl16Otujmu6cCPz1bWK-GY1ogK_9ejicgw/edit#heading=h.fzwcs020kou5)
- Generally, people with >= 2 YOE should watch HLD live. Otherwise first clear backlog of DSA, SQL and watch HLD recordings.
- HLD is a must for senior roles, like >= SDE3.
- HLD is about tradeoff and making useful decisions. It's not about theory, at all.

[Lecture notes](../../../../assets/1-HLD-Basics-and-Consistent-Hashing-pdf-1-864cbb80.pdf)

## Lecture
LLD is concerned about how we can write better code. This means code that is extensible (new features), reusable, maintainable (bug fixes).

System design (HLD) is the study of how different infrastructure layers that work together to server an application at a scale at a desired efficiency. Example of infrastructure layers: LB, App servers, database servers.

We are not going to cover (and it's usually not discussed in interviews):
1. Knowledge - won't cover tangible steps like setting up libraries, components etc. This is because the focus here is on logical design, not implementation. *Whats the best library? Whats the best language*
2. HLD is about problem solving (i.e. ability to make good decisions).
3. No implementation.
4. The output artifact here is a diagram, flow-chart etc.
5. The main thing in interviews and day-to-day jobs is to have an intriguing and useful discussion.

### Why do we need distributed systems?
Q: Why do we even need distributed system? Why don't very simple and intuitive design work?
A: He gives a website "deli.cio.us", a website from 2003 that did webpage bookmarking. He first explains how you need to purchase too things, a static IP address (from ICANN, or AWS) and a domain name (from a domain registrar like GoDaddy, Namecheap). Then you add the static IP address in the domain registrars setting, causing the domain-ip pair to be copied to DNSs around the world. This way, your website becomes accessible to outside users. But majorly, he discusses that due to a large number of users (i.e. high load), a single machine is actually a single-point-of-failure (SPOF) which is highly undesirable. The fact that singular machines cannot handle high-load and also are SPOFs necessitates the need for complex and distributed systems.

So suppose the developer of this site created the website/server and running it on his laptop, how will they get incoming requests? Lets solve this problem (below).
### Ability to receive internet requests on local machine - NAT (extra info)
Suppose you developed a website and are running it on your laptop. Is it possible for this app to get requests from an outside server?

ISP's usually maintain machines running software that's usually called a NAT. It is able to create a full network (say 2<sup>32</sup> private addresses) with just one actual IP address (from ICANN).

- Since IPv4 is deficiency of addresses, the usage of NAT is non-optional. But this has the negative consequence that incoming internet requests are not possible (since a user may be outside of an ISP, and does not know about internal addressing or your address within your ISP).
- Another reason why it's difficult to use local machines as production servers is "dynamic IP", i.e. your ISP can change your assigned IP address. This is not noticeable or relevant in as a user of internet (as compared to being a listening server).

- To fix this, ISP's do provide public-static-IP addresses, on demand.
- An alternative way to get public-static-IP addresses is to directly get it from ICANN, or get it via AWS Route 53.

Ok, now the site would get incoming requests.
- Now, suppose we want to update the site, and suppose this requires restarting the server, and may take some time. This means the website will be inaccessible for some time. We don't want this to happen. The main reason why we have such a characteristic in our website is that we have a SPOF (single point of failure). 
- Another problem can be huge load.

Lets solve these connected-problems (below).

### Load balancers
The simplest way to avoid SPOF is to have multiple app server machines, and add an extra machine called load balancer whose only job is to receive a user request and forward it to one of the app servers. The app server does the work, and responds to the user via the load balancer.

The setup flow is simple: the LB is switched on first. Then we switch on the app servers, and each of them sends a "register" request to the LB. The LB maintains a list of app servers. Note that only the LB needs to have a static IP address, and app servers can have private/virtual addresses (since they don't talk directly to the outside world).

**Algorithms** for distributing load equitably (or LB choosing the most appropriate server to forward a request too):
- Round robin (if all app servers are equally strong). The logic is that the LB maintains a pointer in its list, and keeps advancing it (circularly) for each request.
- Weighted round robin (if all some app servers are more strong then others). The LB still maintains a pointer in its list, but also keeps `currentCount`, `currentPower` variable that equals the relation power of the currently selected app server. The `currentCount` keeps increasing for each request, and when it equals `currentPower`, it resets to 0, the pointer advances. The `currentPower` is also set to the newly pointed app server. This is simple too.
- Handling server death - suppose a server dies. Then the LB just deletes it from its list, and advances the pointer to the next app server in the list (like usual). This is easy to do for weighted round robin too.
Its better to choose simple algorithms in LB, to make sure the LB itself doesn't become a bottleneck. LBs should be strictly lightweight.

**Is-alive mechanisms** used by LBs:
- Heartbeat: the app server keeps sending "I'm alive" every x seconds. If the LB doesn't get a message for x seconds, then it assumes the app server is dead.
- Health-check: the LB sends a request (say HTTP request) "Are you alive?", and if it gets a response then the app server is alive. If no reply, the app server is assumed to be dead.
## Summary
- Module Introduction
- Why do we need distributed system
- DNS and ICANN
- Need of DNS, and how it works
- DNS questions
- Distribution of load
- Working of Load Balancer
- Consistent hashing: not covered in this lecture.
## Assignments
None listed.