You will need to install the following software packages in order to download and run the SickChill development application.  
This guide makes the assumption that your development computer is running Windows 10 or 11 with 64-bit architecture. 
This guide also assumes you have a valid login account with github.  
If you do not have an account, head over to github.com and click on Sign Up in the upper right-hand corner and create an account.

* Git  
  * https://git-scm.com/download/win  
  * Default install settings  
* NodeJS  
  * https://nodejs.org/en/download/  
  * Make sure to install Chocolatey when prompted during the install process  
  * Follow defaults on the Chocolatey cmd window prompts after NodeJS install.  
* Yarn  
  * https://classic.yarnpkg.com/lang/en/docs/install/#windows-stable  
  * Default install settings  

Once you have finished installing Git, NodeJS, and Yarn, you are ready to clone the SickChill repository
1.	Navigate to the main SickChill git repository at https://github.com/SickChill/sickchill
2.	Then click on Fork in the upper right-hand corner
3.	Fork the sickchill repository to your own repository
4.	Open the git command line utility. You must run it as Administrator in order for the dependencies installation to complete successfully. 
5.  Navigate to a folder you wish to install SickChill under.
6.	Now you can clone your own github repo to your computer using the following commands:  
```
    git clone github.com/<<your github username>>/sickchill.git  
    cd sickchill  
    git remote add upstream https://github.com/sickchill/sickchill.git  
    git fetch upstream  
    git checkout -b frontend upstream/develop  
```
7.	Now we are ready to install the SickChill developer instance with the following commands
8.	Run the following commands to install the SickChill dependencies:  
```
    pip install poetry  
    yarn --dev  
    poetry install --with speedups --with frontend --with dev  
```
9.	If you get the following warning when running the poetry install above:  
Warning: poetry.lock is not consistent with pyproject.toml. You may be getting improper dependencies. Run `poetry lock [--no-update]` to fix it.  
Then run poetry lock --no-update – Then re-run the poetry install command afterwards.
10.	Now we can run SickChill in development mode using the new flask webserver:
```
    poetry run sickchill --flask
```  
11.	The new development SickChilll should now be running on port 8082, you can access the development instance by navigating to https://localhost:8082
12.	Happy development!
