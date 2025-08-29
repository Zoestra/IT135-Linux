https://github.com/Zoestra/docker-lab

assignment: clone docker lab, add a quote to index.php, confirm it works, submit.



# from codeshare
08/26/2025:

This week we'll create a Week 8 Class Exercise document named IT135 SM25 Week 8 - Docker/Network Tools.  Today in class we discussed the last mandatory items, of which will be the week 8 class exercises we're talking about now, and your version of the Docker Lab that will sport a favorite quote or two on the index page that you think is cool. That assignment will be Docker lab, but it does not exist at this very moment.

On Thursday, please come to a special session with some IT alums, 7-8pm on Augest 28th:

 https://newmanix.com/web-careers/it-career-check-in.php


Today in IT135 we were introduced to a repo that demonstrates how our LAMP stack could be supported inside Docker containers.  Here's the repo we'll be forking: Docker Lab Repo

08/23/2025:
Final devcontainer.json: Here's the version of devcontainer.json that was NOT available during today's live session in the LAMP doc.  If you're watching the recording, you'll find this at step 16, which is toward the very end of the doc:

```
{

  "name": "LAMP setup",

  "image": "mcr.microsoft.com/devcontainers/base:ubuntu",

  "features": {

    "ghcr.io/devcontainers/features/common-utils:2": {}

  },

 "postCreateCommand": "sudo apt-get update && sudo apt-get install -y git apache2 php libapache2-mod-php mariadb-server php-mysqli",

  "postAttachCommand": "cp -f .bashrc ~/.bashrc && . ~/.bashrc && git pull --all",

  "forwardPorts": [80]

}
```

  

The `postCreateCommand` identifies which scripts and commands to run when we create a new Codespace.  The `postAttachCommand` loads scripts and commands to run every time we connect to the Codespace.  Note `git pull –all` is in the `postAttachCommand` as we may have made changes outside of the Codespace, meaning by editing files in GitHub directly.