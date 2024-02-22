# Lab 
lab link: https://github.com/JayYu0116/MLIP_Lab6/blob/main/Lab6.md
fork: https://github.com/pablo-marin-vicuna/MLIP_Lab6.git

# install jenkins on VM

reference link: https://www.jenkins.io/doc/book/installing/linux/

## First install java
su root
(password)

sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version

openjdk version "17.0.9" 2023-10-17
OpenJDK Runtime Environment (build 17.0.9+9-Ubuntu-122.04)
OpenJDK 64-Bit Server VM (build 17.0.9+9-Ubuntu-122.04, mixed mode, sharing)

## install jenkins
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

#start jenkins
sudo systemctl start jenkins

#success of install
sudo systemctl status jenkins

#unlock jenkins
(in browser) 127.0.0.1:8080
more /var/lib/jenkins/secrets/initialAdminPassword

Give Jenkins sudo permission by running sudo visudo and add line jenkins ALL=(ALL) NOPASSWD: ALL

# Install Miniconda
link: https://docs.anaconda.com/free/miniconda/miniconda-install/

conda create -n mlip python pytest numpy pandas scikit-learn -c conda-forge

## Setting Up Vitual environment
conda activate /home/vboxuser/miniconda3/envs/mlip

# Setting up a Jenkins Pipeline
- Enter Jenkins dashboard: 127.0.0.1:8080 using your web browser.
- Clikc on + new item button on the left.
- Use mliplab6 as your project name and choose pipeline project.
- Under General section, click on Github Project and provide your forked repository http url.
- Under pipeline, click on pipeline definition and choose Pipeline Script from SCM. You need to create personal access token. Then choose git as your SCM. Add a username password credential with any username and your personal access token as the password.
- Change the branch specifier to main. Then, during each build, your Jenkins will pull code from Github and build upon it.




