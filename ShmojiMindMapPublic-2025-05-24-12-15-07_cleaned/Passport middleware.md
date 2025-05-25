  * Key points of what it is
    * Makes it so users can auth through many different platforms (google, twitter, github, etc) with basically same code.
    * Passport does not handle making sure your local DB user is just one user across all platforms, you would have to figure out that logic
    * You can do this logic yourself, but it is gonna be alotttt of code. Doing one type of auth isn't too bad, but once you need more than 1, it gets complicated