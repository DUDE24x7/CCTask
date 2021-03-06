# CCTask

#create an AWS ubuntu 16.04 server
#Security group rules: SSH = port 20 (anywhere - normally I would set My Ip); HTTP = port 80 (anywhere); HTTPS = port 443 (anywhere)

#Copy the script below and run it after accessing the server from SSH

sudo apt-get update;
sudo apt-get install git;
git config --global user.name “Tom”;
git config --global user.email “judgemental1@me.com”;
git config --global core.editor nano;
mkdir gitdownload;
cd gitdownload;
#git init;
git clone https://github.com/DUDE24x7/CCTask.git;
chmod 700 CCTask/AWS1.script;
cd;
echo "AWS1.script is starting";
gitdownload/CCTask/AWS1.script;
echo "AWS1.script has ended";

Afterwards setup Drupal from http://<your_home> and then
Install CiviCRM on Drupal from http://<your_drupal_home>/sites/all/modules/civicrm/install/index.php

Here are the sources of reference material for the task. The task requirement is documented below

NGINX MYSQL PHP
https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-in-ubuntu-16-04

Drupal 7.54
http://idroot.net/linux/install-drupal-ubuntu-16-04/

Configure NGINX for Drupal
http://blog.celogeek.com/201209/202/how-to-configure-nginx-php-fpm-drupal-7-0/
There was nothing to do here.

Install DRUSH http://docs.drush.org/en/7.x/install/
and https://www.digitalocean.com/community/tutorials/how-to-install-drush-on-a-cloud-server-running-ubuntu-12-04

Configure DRUSH http://docs.drush.org/en/7.x/configure/
Nothing to do here either.

Running Drush https://www.digitalocean.com/community/tutorials/a-beginner-s-guide-to-drush-the-drupal-shell

Configure Drupal to have a private files folder - https://www.drupal.org/docs/8/core/modules/file/overview
For a truly private file system the files folder should be located above the public root so that they aren't accessible from the public root

CiviCRM 4.7.19
Note – Default installation is a separate DB for CiviCRM and for Drupal
https://wiki.civicrm.org/confluence/display/CRMDOC/Installing+CiviCRM+for+Drupal+7

CiviCRM extensions https://wiki.civicrm.org/confluence/display/CRMDOC/Extensions#Extensions-Drupal

Backup and recovery script to Amazon S3 using the Backup and Migrate Drupal module
https://www.drupal.org/project/backup_migrate
https://www.lullabot.com/articles/module-monday-backup-and-migrate
https://www.drupal.org/node/2465951

HTTPS on AWS with Cerbot
https://certbot.eff.org/#ubuntuxenial-nginx
https://medium.freecodecamp.com/going-https-on-amazon-ec2-ubuntu-14-04-with-lets-encrypt-certbot-on-nginx-696770649e76
https://coderwall.com/p/e7gzbq/https-with-certbot-for-nginx-on-amazon-linux
https://blog.nikitaog.me/2016/02/12/how-to-setup-ssl-on-amazon-web-services-with-nginx/
https://www.digitalocean.com/community/tutorials/understanding-nginx-server-and-location-block-selection-algorithms

The requirement:
Task 1: Drupal and CiviCRM PCI compliant and secure cloud installation

Create a new PCI compliant server using Nginx on an AWS micro instance (or similar). (done with AWS)

Install Drupal 7 and CiviCRM this server in a secure fashion. You may wish to research what Nginx configurations are required to make both Drupal AND CiviCRM secure. Please install CiviCRM and Drupal in different databases as this is considered best practice. (this is the default)

1 Install Drush to the server for the appropriate user (done)
2 Install Git to the server for the appropriate user (done)
3 Configure Drupal to have a private files folder (done)
4 Configure the CiviCRM extension directory correctly (done)
5 Ensure that the Nginx configuration is secure for CiviCRM (done)
6 Configure Drupal so that Drupal views can use the CiviCRM database (https://wiki.civicrm.org/confluence/display/CRMDOC/Views3+Integration) (not sure if I have done this correctly)

Setup a suitable backup and recovery script to Amazon S3 using the Backup and Migrate Drupal module and document what will be backed up.

Please then send us the following:

1) Create a new github repository for your site and push the configured site to Github. Send us links to the new github repository.

2) Send us links to the site and all server and site root passwords so we can review the configuration.

3) Send us a screenshot or export of the server passing PCI compliance scan (there are several free providers) and full details to login to the server and review the configuration.

4) Send us links to any references for configuration files and/or standards that you have used

(Please note: Use LetsEncrypt for ssl certificates with automated renewal).

Task 2: Automation

Automate the creation of the server above using an automation tool of your choosing. Our preference would be for Ansible as we have some existing infrastructure set up with this but we are open to new ideas.

We recommend to use AWS free tier for hosting

Please then send us the following:

5) Create a new github repository for the automation and send us the link

6) Send us any additional notes or information required to review the build


Task 3: CiviHR SaaS platform (Prepare for technical interview)

CiviHR is an open source Drupal/CiviCRM distribution customised and configured as an HR application for charities. More information can be found here: https://civihr.org/

In preparation for the technical interview please prepare notes on a (very) high level / rough draft of a SaaS platform architecture for CiviHR that can allow us to manage and scale to 1000’s of instances of the application.

State any considerations for client account management, server or other infrastructure management. You are welcome to propose automation such as Chef/Puppet, containerised solutions such as Docker, Heroku or otherwise but please provide reasons for your proposals and some rough costs for 1000 client sites/instances.

If you have time to send us high level notes for our consideration before the interview then these would be a bonus.
