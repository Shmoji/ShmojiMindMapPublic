  * tracking trying to setup EC2 instance to host ExpressJS backend
    * [[2024-06-07]]
      * using the remote ssh extension for VSCode - everytime i try anything - something happens and SSH connection drops and then you cant sign into EC2 instance from anywhere. 
      * i think MAYBE if you completely close VSCode, you can now sign in through AWS console again (test this again). Tested again and i must have been wrong - must be a time thing - you just gotta wait x amount of time after using x amount of whatever resource was maxed out and caused SSH disconnect. EDIT: dont think a time thing. You just gotta find a way to reset broken isntance
      * think it's possible the limits of the AWS free tier are strong and plague you with bugs. One thing: may only be able to SSH from one place at a time on free tier
      * learned trying to open tsconfig file causes ssh to disconnect forever bc it tries to init ts stuff and some reason that breaks the EC2 instance. I think bc free tier instance runs out of memory
    * [[2024-07-26]]
      * i noticed after creating load balancer and using load balancer URL, i can instantly see http server index file from /var/www/html by going to url in browser, but cannot instantly get running expressjs api to work by going to url. Which is weird bc ec2 public ip4 does already work for this
      * solution to above: i had to recreate the target group except set the port as 3300 (what i defined in my backend express app that is running on ec2) and everything else can stay same - including keeping it as http...for now (i wonder if changes later)
      * also noticed load balancer url didnt need port in it after the above too
      * ran into this question: ((-bQ8uQw5t))
  * HOW TOs
    * [[how to use HTTPS for backend endpoint]]
  * questions
    * can i run express api on EC2 instance without load balancer? trying to lower costs ^IUsVmUVQg
      * Yaniv Rozenboim on repost aws forum
        * You don't necessarily need load balancer. Just keep in mind that you lose the scalability and high availability that a load balancer provides. (e.g., if you have any sort of failure or surge in traffic your application might be unavailable).
        * Yes. You can expose your EC2 instance directly using public IP or by assigning Elastic IP to the instance without using a load balancer. it's actually simpler in terms of setting it up compared to use load balancer.
      * Leo K on repost aws forum
        * To clarify, a load balancer won't improve availability or scalability with just one EC2 instance in any significant way. It could filter out malicious or unnecessary requests, if properly configured to do so, but in this case, the most likely value from the load balancer is that it allows terminating TLS with a certificate issued by Amazon Certificate Manager (ACM) at no additional cost. To use HTTPS without a load balancer or CloudFront, a TLS certificate would have to be obtained from a third party certificate authority and maintained either manually or with a third-party automation. ^4ijLQWYky
      * me: it seems getting 3rd party cert may not be too hard, but then installing that cert and maintaining it everytime it expires may be hard and time consuming
    * can you use load balancer DNS name as backend endpoint?
      * you cant. it will work with HTTP, but not fully with HTTPS bc you dont OWN that domain - AWS does - and this causes issues with the certificate somehow