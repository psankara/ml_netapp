## Agenda ##

* Restart our VMs from last time

* Build a Docker image that has python3, numpy and pandas

Modify the Dockerfile to include python3, numpy and pandas. Do this sequentially, running the container after every build to see the effect of every modification. Layers get added to the same container image with every modification.
```
e.g. : pip3 install numpy
```
Other packages to install:
```
scipy pandas matplotlib
```

* Enhance the image to include a Jupyter environment

Jupyter is IPython, or interactive python. It is a great programming environment for learning and later for EDA.
```
pip3 install jupyter
```

* How can we make the container boot to the bash shell

Try running the container without specifying the command to run. What happens?
```
Hint: CMD ["bash"]
```

* Start container with an external mount

In order to preserve, and commit your notebooks to git, we can run use a mount to store our Jupyter notebooks.
```
docker run --rm -it -v /home/vijjus/ML_sessions/session_2:/code pycontainer
```

* Start a Jupyter notebook

First we need to enable port 8888 in our VM's firewall. Once we do this, we can run the container with access to the host network (--net=host) to access our Jupyter notebooks.

```
jupyter notebook --ip 0.0.0.0 --allow-root
```
Jupyter runs by default on the loopback IP. Find the external IP of your VM, and connect to port 8888 on that IP using your browser. Note: incognito mode is preferred since Jupyter uses cookies. Also, we will need to enter our secret.

* Explore some basic numpy code

Remember to "Save and checkpoint" and logout.
