# AI LA Open Innovation Challenge, Fall 2022

Hello!

Well, now that we've been introduced, here's something practical.

## RTI Data Challenge

If you are working on the RTI Challenge, you have been given a virtual machine on DigitalOcean to house the data and process your scripts.  Please **DO NOT** download the data.  Very bad things will happen.

### Using Jupyter
You probably wish to use Jupyter to do your explorations, like provided in the demo lecture.  This requires a small amount of setup.

#### Activate your virtual environment

Ssh as root into your machine.  Open a terminal then do 

```
ssh root@<your.ip.addy>
> <your password>
```

Check to see if you have a `.venv` folder already installed in your home directory:

```
ls -alh 
total 64K
drwx------ 10 root root 4.0K Sep 18 19:42 .
drwxr-xr-x 20 root root 4.0K Sep 18 20:12 ..
-rw-------  1 root root  922 Sep 23 02:15 .bash_history
-rw-r--r--  1 root root 3.1K Oct 15  2021 .bashrc
drwx------  4 root root 4.0K Sep 17 21:39 .cache
-rw-r--r--  1 root root    0 Sep 18 20:10 .cloud-locale-test.skip
drwx------  5 root root 4.0K Sep 17 21:39 .config
drwxr-xr-x  3 root root 4.0K Sep 17 21:35 .ipython
drwxr-xr-x  2 root root 4.0K Sep 17 21:34 .jupyter
-rw-------  1 root root   20 Sep 18 19:38 .lesshst
drwx------  3 root root 4.0K Sep 17 02:11 .local
-rw-r--r--  1 root root  161 Jul  9  2019 .profile
-rw-------  1 root root    0 Sep 18 19:42 .python_history
drwx------  2 root root 4.0K Sep 17 02:09 .ssh
drwxr-xr-x  7 root root 4.0K Sep 17 21:23 .venv   # Your python virtual environment
-rw-------  1 root root  985 Sep 17 21:22 .viminfo
-rw-r--r--  1 root root  185 Sep 26 22:24 .wget-hsts
drwx------  3 root root 4.0K Sep 17 02:09 snap
```

If you don't, go ahead and create one in your home dir.  You can put it anywhere you like but this makes it easy. Then source it to enter the virtual environment.

```
root@brian:~# python3 -m venv .venv
root@brian:~# source .venv/bin/activate
(.venv) root@brian:~#
```

Note the `(.venv)`. Cool, now we want to add the requirments.  Those are listed in a folder under the data directory.

```
pip install -r /data/RTI_Rarity-AILA/requirements.txt
```

Note, **YOU ONLY HAVE TO DO THE ABOVE BIT ONCE**.  But if you do it again it won't hurt.

#### Set Jupyter Password

If you don't do this, DigitalOcean will not serve your notebooks.

```
jupyter notebook password
> "super secret password you do not share"
```

Really, don't share this with anyone outside your team.  Remember this is PHI and you need to be careful with this data.


#### Start Jupyter

You need to have sourced the venv every time you log in, and now you can start Jupyter.  It's easiest if you do it from the data directory.  So we'll change directories and start Jupyter.

```
cd /data
jupyter notebook --allow-root --no-browser --ip="*"
```

Now you should be able to navigate to `<your ip>:8888` and get ur notebuk on, bro.

**WARNING** Sometimes when you copy and paste it won't take the command.  Retype the above in the `/data` directory and you should be fine. Do note the `--` is TWO minus signs, not one.

Please shut down Jupyter when you're done.  This is for security reasons.

HAPPY HUNTING! If you run into problems, find me (Brian Dolan) on Discord: buddha_314#1897
