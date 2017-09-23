# Jenkins getting started on Docker

## Requirements
* docker


## Setup
Build docker image by
```bash
docker build -t jenkins-master .
```

Start a container by
```bash
docker run -p 8080:8080 -p 50000:50000 \
-v `pwd`/jenkins_home:/var/jenkins_home -d jenkins-master
```

Open http://localhost:8080 with a browser.
You can see the Jenkins page.

Password will be required to login.
You can find the password by
```bash
cat `pwd`/jenkins_home/secrets/initialAdminPassword
```

After you logged in, you will be asked whether to install plugins.
Choose `Install suggested plugins`.  

After plugins are installed, the page for creating admin user shows up.
Create some account, and you can now have Jenkins' dashboard.
