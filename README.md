# CCTask

#create an AWS ubuntu server

#Copy the script below and run it after accessing the server from SSH

sudo apt-get update;
sudo apt-get install git;
git config --global user.name “Tom”;
git config --global user.email “judgemental1@me.com”;
git config --global core.editor nano;
mkdir gitdownload;
cd gitdownload
git init;
git clone https://github.com/DUDE24x7/CCTask.git;
chmod 700 CCTask/AWS1.script;
cd;
gitdownload/CCTask/AWS1.script;
end;
