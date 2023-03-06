# mongoDB-windows

# How to install MongoDB server (Not Mongo Atlas) for Windows:


## Step 1 — Download the MongoDB MSI Installer Package
Head over here (https://www.mongodb.com/try/download/community) and download the current version of MongoDB. Make sure you select MSI as the package you want to download.


## Step 2 — Install MongoDB with the Installation Wizard

  A. Make sure you are logged in as a user with Admin privileges. Then navigate to your downloads folder and double click on the .msi package you just downloaded. This will launch the installation wizard.

  B. Click Next to start installation.

  C. Accept the license agreement then click Next.

  D. Select the Complete setup.

  E. Select “Run service as Network Service user” and make a note of the data directory, we’ll need this later.

  F. We won’t need Mongo Compass, so deselect it and click Next.

  G. Click Install to begin installation.

  F. Hit Finish to complete installation.


## Step 3— Create the Data Folders to Store our Databases

  A. Navigate to the C Drive on your computer using Explorer and create a new folder called data here.

  B. Inside the data folder you just created, create another folder called db.


## Step 4 — Setup Alias Shortcuts for Mongo and Mongod
Once installation is complete, we’ll need to set up MongoDB on the local system.

  A. Open up your Hyper terminal running Git Bash.

  B. Change directory to your home directory with the following command:
    $ cd ~

  C. Here, we’re going to create a file called .bash_profile using the following command:
    $ touch .bash_profile

  D. Open the newly created .bash_profile with vim using the following command:
    $ vim .bash_profile

  E. In vim, hit the I key on the keyboard to enter insert mode.

  F. In your explorer go to C → Program Files → MongoDB → Server
    Now you should see the version of your MongoDB.

  G. Paste in the following code into vim, make sure your replace the 4.0 with your version that you see in explorer

    For mongo db 6.0 use :
      alias mongod="/c/Program\ files/MongoDB/Server/6.0/bin/mongod.exe"
      alias mongo="/c/Program\ Files/MongoDB/Server/6.0/bin/mongos.exe"


## Step 5 — Verify That Setup was Successful

  A. Close down the current Hyper terminal and quit the application.

  B. Re-launch Hyper.

  C. Type the following commands into the Hyper terminal:
    $ mongo --version

  Once you’ve hit enter, you should see something like this:

    mongos version v6.0.4
    Build Info: {
        "version": "6.0.4",
        "gitVersion": "44ff59461c1353638a71e710f385a566bcd2f547",
        "modules": [],
        "allocator": "tcmalloc",
        "environment": {
            "distmod": "windows",
            "distarch": "x86_64",
            "target_arch": "x86_64"
        }
    }

This means that you have successfully installed and setup MongoDB on your local system!
