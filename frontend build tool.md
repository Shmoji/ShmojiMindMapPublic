  * what is it?
    * GPT4:
      * in web development is a software application that automates various tasks and processes related to preparing your web application's code for production
      * popular frontend build tools include [[webpack]], [[vite]], Gulp, and Grunt, each offering different features and specializing in various aspects of the build process (sometimes they pick specific purposes, so good to be aware of that)
      * The main purposes of a frontend build tool include:
        * Code Transpilation: Converting modern JavaScript (ES6+) into a version compatible with older browsers using tools like Babel. This ensures that newer syntax and features work across different browser environments.
        * Module Bundling: Combining multiple JavaScript files (modules) into a single file or a few files. This reduces the number of HTTP requests needed to load a web page, improving load times. Tools like Webpack and Rollup are popular for this purpose.
        * Minification and Compression: Reducing the size of code and asset files by removing unnecessary characters (like whitespace and comments) and compressing them. This process decreases the amount of data that needs to be transferred over the internet, leading to faster page loads.
        * CSS Preprocessing: Transforming CSS written in languages like Sass or LESS into standard CSS. These languages offer features not available in plain CSS, like variables, nested rules, and mixins.
        * Image Optimization: Compressing image files without significant loss of quality to ensure faster page loads.
        * Hot Module Replacement (HMR): Updating modules in the browser while preserving the application state, providing a faster and more efficient development experience.
        * Linting and Formatting: Analyzing code for potential errors and enforcing a consistent coding style using tools like ESLint and Prettier.
        * Dependency Management: Managing external libraries or packages your application relies on. Tools like npm or Yarn are used to install, update, and manage these dependencies.
        * Automating Tasks: Running repetitive tasks like testing, deployment, and custom scripts efficiently.
