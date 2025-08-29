# Prompt
Please watch the following videos and be prepared to answer a few questions:

![What is the LAMP Stack?](https://www.youtube.com/watch?v=WY8jwTNYTfg)

![https://www.youtube.com/watch?v=Sxxw3qtb3_g](https://www.youtube.com/watch?v=Sxxw3qtb3_g)

![https://www.youtube.com/watch?v=Gjnup-PuquQ](https://www.youtube.com/watch?v=Gjnup-PuquQ)

![https://www.youtube.com/watch?v=PziYflu8cB8](https://www.youtube.com/watch?v=PziYflu8cB8)



1) **critical thinking** in the first video, the author explains how the web server passes the request first to php to process the page, which potentially retrieves data to add to the page from mysql.  what does this say about viewing the source of the page finally delivered?  can we retrieve the php code that produced the page by viewing the page source?  why or why not?

2) **Critical Thinking** In the second video, even though there are a large number of options available for most technologies, the front end language always appears to be JavaScript.  Do you know why this is?  If so, please explain.

3) In the second video, the author explains that while in his opinion MongoDB can scale to support more data, it's not as popular as relational databases such as MySQL or PostgreSQL.  Why would this be so?  Do you have any suggestions or preferences?  Please explain.

4) In the third video the author explains why containers are more efficient than VMs.  How would you explain this in an interview?

5) In the fourth video, the author explains how Kubernetes orchestrates containers.  What is a pod in this case and what is it's purpose?

6) What are some factors to consider when choosing an application stack on which to develop your web application?

7) If you have experience working with application stacks or containers, please share your experience.  Do you work with a particular stack?  If so, why?


**Comment On The Post of Another (Required):** Once you have placed your comment, please come back and read the posts of others and place at least one **quality** comment in relation to another post.


# Submission

 1. we cant see the PHP code by looking at the page source, because the PHP code generates the HTML (the page source), but is not contained by it. The PHP code is executed server-side and only the resulting HTML is sent to the user. 

2) Javascript can be natively read by all browsers, and is specifically designed for web. Beyond that, Javascript has enormous momentum, which means it has a huge base of libraries, many different frameworks to choose from, and a lot of highly experienced professionals who already know it.

3) the video doesnt really give a lot to work with here, but from my experience in my databases class, MongoDB works more like a dictionary where you can add whatever key/value pairs you want for that record, but the SQL based DB's you need to plan out ahead of time what columns each table will have. this means that you can build a much more rigid model of your DB. Stability is often more important than that flexibility, depending on your application. 

4) when multiple VMs are running, they each run their own version of the guest OS, whereas containers share one kernel between them. with VM's, there is greater overhead due to this kernel duplication. 

5) A pod is a set of containers which are treated as a group. usually, each container is serving one client. this allows for rapid scaling as demand for the service grows or shrinks

6) The most important thing to consider is what the actual scale of your service is. theres a running joke in some circles about apps that have more microservices than users. You should only be as complex as you need to be, and you shouldnt just go chasing new frameworks.

7) I run FoundryVTT on my home server, its an app for running tabletop roleplaying games online, like a self-hosted version of Roll20. I run it all off of a raspberry pi, and i use Portainer to manage my containers. I have a container which runs foundry v11, which is what i need for my Cyberpunk Red game, and this setup means that if i want to start a DnD game, whose system supports foundry v13, i could easily set up another container running that server. Foundry uses Node as its server host.  I also have a container running Nginx, which acts as a reverse proxy for my server, providing extra security.  
