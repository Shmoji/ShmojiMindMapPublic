  * Questions
    * Is indexing experiences by "what does the experience feel like" too limiting? Is "what was the experience like" better?
    * Can the definition of a word be an experience? Can the use cases of a word be an experience? I think so, but the wording just seems off, which makes me think using "add experience" doesn't work. But what can be used to cover experiences AND software built on top of experiences?
    * Why would a user want to share their experiences? (why would Tyler, James, nana, etc share?)
      * Reasons everyone would agree with
        * To make money. 
        * To get attention that is public. User sees that many people see them as someone getting attention. This can lead to making money.
      * Reasons most wouldn't agree with
        * To help society by adding info to the internet so people can compare their experience to yours (love)
        * To find people that relate or like their experience. Or maybe to get unexpected comments on their experience that they never thought about (discovery, social connection, fun, attention)
        * People enjoy sharing stuff online. Ex: Twitter, FB, reddit. (fun)
        * People feel they will be rewarded with something if they share online
        * To get it out of their head to solidify it and not forget it (memory)
    * Why would a user want to have access to individual experiences from people around the universe?
      * To compare to their own experiences
  * Use Cases
    * For people to figure out mysterious health issues
    * To list all unknown of human knowledge
    * To list all desires of human knowledge
    * To list all experience of living creatures
  * Visuals for frontend
    * First thing when you open site or app
      * It says "which do you want?" Has two options: to share experience to view experiences. This just decides what is seen next: input experience form or regular home site
  * Ideas for names

    * howdoesitfeel.c om
    * whatdoesthatfeellike.c om
    * whatisitlike.co m
    * thatfeeling.c om
    * feeling.c om
    * feelingexplained.c om
    * feelingsexplained.c om

    * XP.c om (i like this). I imagine app name and brand name like "XP - how does it feel?"
    * HX.c om. human experience database
    * XP Tracker
    * Experience Tracker
  * Brainstorming twitter idea

    * Auth using Twitter

    * User flows

      * User posting experience

        * They start tweet thread with "what it's like to have sinus infection experience hashtag" . 
  * Brainstorming what it will look like
    * There will be a header with a search bar. Here you can look up any feeling. As you type, suggestions will pop up based on text. The first option will be whatever text is and pressing enter searches it. This is exactly how Quora works.
    * There will be "Add feeling" button. You add "what is being felt"/"experience" and you add "what does it feel like" and you add "confidence that experience and feeling are related". "What is being felt"/"experience" will be just like quora and recommend it if it's already there. 
  * Brainstorming
    * Start off and entire site is free to use. Then, offer the option to turn posts into Ideamarket posts in order to earn income when someone rates the post. People would rate 0-100 if they felt the same way about x thing. This leads to issue of why would someone rate when it costs money, but doesn't earn them any money.
    * Terminology
      * "add feeling" feels like the average joe will think that means to only add mental or physical feelings.
      * "add experience" seems best because they will add both, but experience is basically an indexed version of the feeling. Also, experiences can be nouns like "kidney stone". 
      * There are certain experiences that aren't exactly felt. Like when someone is depressed, they sometimes FEEL nothing. Some surgeries, person feels nothing. But really they did if they had eyes open.
      * I tend to thing of "feeling" as anything observed from all sensory organs. But i dont think most people think of it that way. I tend to think of "feeling" as closer to the physical. The less physical the feeling, the less it feels like a feeling
      * May be better to say "what was experience like" rather than "what did it feel like"
    * Experiencing the definition of a word doesn't sound like a real experience. But in my opinion, it is an experience.
  * Brainstorming UX
    * Maybe should allow user to enter xpCategory or not. Optional.
  * Data Structures for project
    * ExperienceCategory Table
      * Experience title - string (how experiences are indexed. Goal is to be like Quora's questions)
    * ExperienceExplanation Table
      * Experience details - string (what the experience was like for the user)
      * postedBy (wallet that posted the experience)
    * User table

  * Login and Users
    * Differences between SIWE and ideamarket login
      * When checking if user is actually owner of wallet they are trying to change data for, SIWE checks the siwe session variable to know. This is completely on backend. When checking on IM, it checks a JWT, which has to be stored in global state on frontend and bit of frontend logic due to that.
      * IM backend verifies wallet is true owner by using .eth.recover, which takes in signature and message to calculate a wallet address. SIWE uses their logic using SiweMessage.validate and takes message.
      * I think maybe the benefit of JWT in IM is that you don't have to ping backend every single time user loads page to check if they are logged in. However, SIWE seems to have no way for frontend to check if logged in, so would have to ping backend i think.