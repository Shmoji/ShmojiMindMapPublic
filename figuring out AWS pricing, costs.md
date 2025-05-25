  * tracking what im being charged for
    * [[2024-07-29]]
      * currently with no traffic - just ec2 express app not being used, im getting charged for 1) load balancing 2) elastic compute cloud - compute 3) elastic block store
  * tracking load balancer costs
    * [[2024-07-29]]
      * had load balancer not even being used, but it's online and connected to EC2 express app running - and it is costing 54 cents per day - charging for 24H each day. in one month this would be about $15 just for load balancing and it's not even doing anything. Would activity on the actual website increase the costs - i assume it would - and i wonder how significant it would be
  * tracking amazon elastic compute cloud - compute costs
    * [[2024-07-29]]
      * when not even being used, just running ec2 express app, it costs 28 cents per day
  * tracking amazon elastic block store costs
    * [[2024-07-29]]
      * when not even being used, just running ec2 express app, it costs 2 cents per day