# Linux Fundamentals Part 3 - TryHackMe

## 1. Terminal Text Editors

- Nano: to create or edit a file using nano, use `nano filename -- replacing "filename"` with the name of the file you wish to edit. Example: `nano myfile`.

- VIM: is a much more advanced text editor.
Some of VIM's benefits:
- Customisable - you can modify the keyboard shortcuts to be of your choosing.
- Syntax Highlighting - this is useful if you are writing or maintaining code, making it a popular choice for software developers.
- VIM works on all terminals where nano may not be installed.
- There are a lot of resources such as cheatsheets(opens in new tab), tutorials, and the sorts available to you use.


## 2. Useful utilities

- `wget`: This command allows us to download files from the web via HTTP

- `scp`: a means of securely copying files. Example: scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt.
Working on a model of SOURCE and DESTINATION, SCP allows you to:
- Copy files & directories from your current system to a remote system.
- Copy files & directories from a remote system to your current system.

## 3. Processes

### Viewing Processes

- `ps`: use to provide a list of the running processes as our user's session and some additional information such as its status code, the session that is running it, how much usage time of the CPU it is using, and the name of the actual program or command that is being executed. To see the processes run by other users and those that don't run from a session, we need to provide aux to the `ps` command like so: `ps aux`.

- `top`: gives real-time statistics about the processes running on system instead of a one-time view.

### Managing Processes

- `kill`: to kill a command, we can use the appropriately named kill command and the associated PID that we wish to kill, to kill **PID 1337**, we'd use `kill 1337`.

Below are some of the signals that we can send to a process when it is killed:

    - SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
    - SIGKILL - Kill the process - doesn't do any cleanup after the fact
    - SIGSTOP - Stop/suspend a process

### How do Processes Start?

The Operating System (OS) uses namespaces to ultimately split up the resources available on the computer to (such as CPU, RAM and priority) processes. Processes within that slice will have access to a certain amount of computing power, however, it will be a small portion of what is actually available to every process overall. Namespaces are great for security as it is a way of isolating processes from another only those that are in the same namespace will be able to see each other.

**systemd**: is one of the first processes that are started. Any program or piece of software that we want to start will start as what's known as a child process of **systemd**.

### Getting Processes/Services to Start on Boot

`systemctl`: this command allows us to interact with the systemd process/daemon. Example: `systemctl [option] [service]`


## 4. Automation

**cron**: process, but more specifically, how we can interact with it via the use of crontabs. Crontab is one of the processes that is started during boot, which is responsible for facilitating and managing cron jobs.

A crontab is simply a special file with formatting that is recognised by the cron process to execute each line step-by-step. Crontabs require 6 specific values:

- MIN: What minute to execute at
- HOUR: What hour to execute at
- DOM: What day of the month to execute at
- MON: What month of the year to execute at
- DOW: What day of the week to execute at
- CMD: The actual command that will be executed.

Crontabs can be edited by using `crontab -e`, can select an editor (such as Nano) to edit your crontab.

## 5. Package Menagement

### Introducing Packages & Software Repos

When developers wish to submit software to the community, they will submit it to an  "apt" repository. If approved, their programs and tools will be released into the wild. Two of the most redeeming features of Linux shine to light here: User accessibility and the merit of open source tools.

Additional repositories can be added by using the `add-apt-repositorycommand` or by listing another provider.

### Managing Your Repositories

Normally we use the apt command to install software onto our Ubuntu system. The apt command is a part of the package management software also named apt. Apt contains a whole suite of tools that allows us to manage the packages and sources of our software, and to install or remove software at the same time.
One method of adding repositories is to use the add-apt-repository command we illustrated above, but we're going to walk through adding and removing a repository manually. Whilst you can install software through the use of package installers such as dpkg, the benefits of apt means that whenever we update our system -- the repository that contains the pieces of software that we add also gets checked for updates. 

## 6. LOGS

Located in the /var/log directory, these files and folders contain logging information for applications and services running on system.

These services and logs are a great way in monitoring the health of your system and protecting it. Not only that, but the logs for services such as a web server contain information about every single request - allowing developers or administrators to diagnose performance issues or investigate an intruder's activity.