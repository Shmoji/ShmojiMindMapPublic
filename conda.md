  * how TOs
    * how to use from command line
      * install from their website
      * if you dont choose option to add to path variable
        * create environment variable and do dis: [python - Add conda to my environment variables or path? - Stack Overflow](https://stackoverflow.com/questions/50906037/add-conda-to-my-environment-variables-or-path)
    * how to create new conda environment
      * %ANACONDA_INSTALL_DIR%\Scripts\conda create --name whisperx python=3.10
    * how to activate environment you created
      * %ANACONDA_INSTALL_DIR%\Scripts\activate whisperx
    * how to see all conda envs
      * conda env list
    * how to find code for installed packages in conda envs
      * On Linux and macOS, in /home/username/miniconda3/envs/ or /home/username/anaconda3/envs/.
      * On Windows, in C:\Users\username\Miniconda3\envs\ or C:\Users\username\Anaconda3\envs
      * Find the Package Directory: Inside this environment directory, look for a Lib folder on Windows (or lib on Linux and macOS)
      * Find "site-packages"
      * then find the package you installed
  * questions
    * what to do if trying to install package, but cant bc says PackagesNotFoundError?
      * conda config --add channels conda-forge
        * this worked last time yay
  * if debugging and STUCK, read this:
    * run windows command line as admin