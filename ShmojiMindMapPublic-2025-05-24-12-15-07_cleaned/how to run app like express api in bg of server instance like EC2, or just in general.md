  * how to actually do the running in bg part:
    * you have to yarn run build express app outside of EC2 or you get out of memory error. Then, need to winscp dist folder to ec2 instance. Before this you need to use winscp tool to import your ec2 pem file to ppk file in order to login to ec2 using winscp
    * then, run: nohup yarn run start &
    * "ps x" to check if it running
  * tracking thoughts
    * tracking thoughts on how to run expressjs api in ec2 instance without load balancer
      * [[2024-07-25]]
        * use this tut https://www.youtube.com/watch?v=T-Pum2TraX4
        * got stuck because i had to use sudo yum install instead of sudo apt-get install - i was using linux ami instead of ubuntu
        * i installed nvm on my own instead of installing node the way he did
        * seems when not using load balancer, maybe dont even need to accept http or https traffic but idk. but you do have to go to security group of instance and add inbound rule for your apis port
        * im at point where trying to use nohup to run my express server on ec2 - at same time i also went to public url to test it and around this time the ec2 just exploded and no longer worked- whyyyyy. only fix was to force stop and start again
        * ended up that using npm run dev caused bugs, so had to use yarn in ec2 instance nice
        * got Public IPv4 address working, but only http and not https which i think is required for a frontend to use the api
        * so now i have this question: can you run express api on ec2 instance without load balancer and still access the endpoint using HTTPS? you can defs do with HTTP, but idk about HTTPS
        * so it seems like a pain in the ass with or without load balancer. Seems like technically you only need load balancer if you expect random giant traffic increases. BUT might as well set it up anyways - and i have no idea if it's possible to keep its price down bc i rememebr that shiz being expensive for that short week of vibecamp

  * use this if you wanna use load balancer: [[how to use HTTPS for backend endpoint]]
  * questions
    * is load balancer needed to have expressjs api run on ec2?
      * i dont think so, but maybe adds more security or something
