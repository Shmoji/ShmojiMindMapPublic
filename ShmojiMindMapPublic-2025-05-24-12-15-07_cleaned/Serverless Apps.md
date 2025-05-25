  * How to use [[AWS lambda]]
    * Best basic tutorial to set it up. Doesn't include setting up endpoint. To do that you need API trigger like [[API gateway]] (another AWS service with free tier) https://blog.jakoblind.no/aws-lambda-github-actions/
    * Endpoint can be acquired through API gateway OR function URL. API gateway is for quick response times, scalable APIs, etc. Function URL is for long response times, etc. Honestly, hard to tell which i want without experience. 
  * Automatic deployments
    * Controlled inside .github/workflows/.yml file
    * Use this GitHub action to make it easier https://github.com/serverless/github-action
