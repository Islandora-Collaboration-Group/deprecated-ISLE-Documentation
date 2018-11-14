# Installing Required Software to Run ISLE
The following pieces of software are required to run ISLE: Docker CE, Docker-compose, and git. This document will walk you through the installation of these components based on your OS:

- [Ubuntu](#ubuntu)
- [CentOS](#centos)
- [Mac](#mac)
- [Windows](#windows)

---

## Ubuntu

### Step 1: Install Server Prerequisites and Git

* Open a terminal on your local laptop or workstation and ssh to the CentOS server / VM:

* You need to become root first

     * If you are not already root, use either `sudo -s` or `sudo su` to become root.

* Install the following:

     * `apt-get update`

     * `apt-get upgrade`

     * `apt-get install -y openssl git htop ntp wget curl nano apt-transport-https ca-certificates software-properties-common`

### Step 2: Install Docker

* `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`  

* `add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`  

* `apt-get update`  

* `apt-get install -y docker-ce`  

* Check if Docker is running `systemctl status docker`

### Step 3: Install Docker-Compose

* Copy and paste the command below

```

  curl -L https://github.com/docker/compose/releases/download/1.20.1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

```

* `chmod +x /usr/local/bin/docker-compose`

* Test the Installation

    * `docker-compose --version`

**Example output:**
```
docker-compose version 1.20.1, build 1719ceb
```

---

## CentOS

### Step 1: Install Server Prerequisites and Git

* Open a terminal on your local laptop or workstation and ssh to the CentOS server / VM:

* You need to become root first

    * `sudo su`  

* Add the RHEL/CENTOS epel-release package repository first

     * `yum install -y epel-release`

* Install the following:

     * `yum install -y openssl git htop ntp wget curl nano`

### Step 2: Install Docker

* `yum install -y yum-utils device-mapper-persistent-data lvm2`

* `yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo`

* `yum install -y docker-ce`

### Step 3: Install Docker-Compose

* Copy and paste the command below

```

  curl -L https://github.com/docker/compose/releases/download/1.20.1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

```

* `chmod +x /usr/local/bin/docker-compose`

* Test the Installation

    * `docker-compose --version`

**Example output:**
```
docker-compose version 1.20.1, build 1719ceb
```

---

## Mac

### Step 1: Git Installation
In order to get a copy (clone) of the current ISLE project, git will need to be installed. [Git](https://git-scm.com) is a software version control system for tracking changes in computer files and coordinating work on those files among multiple people.

 * Open a terminal and enter: `git --version`.

   * This command will inform the enduser if git is already installed.  

```
$git --version
git version 2.15.1
```

  * If git is not installed, running that previous command may trigger the `Install Command Line Developer Tools` prompt. If the prompt appears:
       * Click on the blue `Install` button for the license agreement.
       * Click the white `Agree` button.
       * The package will take 1-2 minutes to download.
       * Click the `Done` button once finished.

  * If git is not installed and the prompt doesn't show, then follow one of the recommended methods for installing git in this nice [tutorial](https://www.atlassian.com/git/tutorials/install-git)

If git is already installed, then please proceed to the next section.

### Step 2: Docker for Mac Installation

* Open a browser and navigate to [Docker Desktop](https://www.docker.com/products/docker-desktop)

* Click the `Download for Mac` button in the center of the page

* Click the `Please Login to Download` button on the right of the page (Login or click `Create Account`)

* Click the `Get Docker` button on the right of the page

* The `Docker.dmg` file should start to download. Check your `Downloads` directory

* Double-click the `Docker.dmg` file. The file should open and mount in a new window / prompt.

* As instructed within the prompt, drag and drop the whale icon to the right towards the `Applications` directory shortcut, a tiny green plus sign should appear, now let go from the mouse or trackpad.

* The application should start to copy data to the `Applications` directory, this process may take 1 - 5 mins depending on the speed of your hard-drive.

* Launch the `Docker` application from the `Applications` directory

* This process should may take 2 -5 mins depending on the speed of your hard-drive.

* Once fully started, one can see a whale icon at the top of their screen. If this is clicked, a dropdown should appear indicating that Docker is now running.
  * Please note: This process also installs the newest version of `Docker-Compose`.

---

## Windows

### Step 1: Git Installation
In order to get a copy (clone) of the current ISLE project, git will need to be installed. [Git for Windows](https://gitforwindows.org/) is a software version control system for tracking changes in computer files and coordinating work on those files among multiple people.

Dowload the installer and run.  The installer will prompt for several choices.  Generally, you should be okay with defaults except:

* Change "use vi" to either Notepad++ (if installed) or nano.  Vi can be difficult to learn and Notepad++ and nano are simpler choices for those unfamiliar with vi.

If git is already installed, then please proceed to the next section.

### Step 2: Docker for Windows Installation

* Go to [https://store.docker.com/editions/community/docker-ce-desktop-windows](https://store.docker.com/editions/community/docker-ce-desktop-windows)

* Choose the "Get Docker CE for Windows (stable)" link to download the installer. You may need to create an account on Docker.com to continue.

* Run the installer and follow the prompts.  The default settings should be okay.

* You will be required to logout when the installation is complete.  

* After logging back in, Docker will run automatically.  

* If you are asked to enable Hyper-V and Containers, click to continue.  

* Your system will reboot after a few minutes.

* Once fully started, one can see a whale icon in the notification area.  

* If you are prompted to log in to Docker, you can choose to do so with your Docker.com account information, or you can simply close the window.  Docker is running and you do not need to log in to use it.

* Please note: This process also installs the newest version of `Docker-Compose`.
