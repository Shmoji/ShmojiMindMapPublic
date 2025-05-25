
  * my knowledge is specifically for expressjs app on EC2 instance. HOW TO:
    * https://www.youtube.com/watch?v=JQP96EjRM98 this tut works. Here are the only diffs:
      * ask GPT: you can use nohup to run npm start in bg so it's still running even when you disconnect from ec2 terminal
      * assuming your expressjs app is running on 3300, you need to create the target group he mentions in exact same way EXCEPT use port 3300
      * in video, he uses hosted zone and route53 - i dont use that at all bc my domain is registered on cloudflare. what i did instead:
        * copy DNS name of my load balancer. in cloudflare, create cname record with this DNS name as value
        * use ACM to create certificate for custom domain like he does in vid - EXCEPT have to validate by adding cname in cloudflare (and cant be proxied in cloudflare)
        * in ur load balancer, add listener for HTTPS and use this certificate
      * the redirect of HTTP to HTTPS in load balancer just doesnt work for me. it causes infinite redirects and breaks everything. So i just have to have HTTP returning results to i guess
      * how it works
        * me: it seems you create ALB, then create target group and register your EC2 instance and include as pending and then set listeners and routing of ALB to forward to that target group. Then you set cname of your custom domain to point to dns of load balancer and make sure LB listens for HTTPS and has certificate from ACM