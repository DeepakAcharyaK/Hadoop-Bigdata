Setup the Hadoop cluster using docker
--------------------------
git clone https://github.com/big-data-europe/docker-hadoop.git #to create the docker-compose file  

cd docker-hadoop 

vim docker-compose.yml #to see all the service 

docker-compose up -d #run in detachable mode ie, run in background it will create and run the containers.

docker container ls #display the containers created by the dockers

docker exec -it namenode /bin/bash  #to execute the namenode serive in interative terminal mode, execute in bin bash mode.

Now you are inside the local file system ie, Linux.  

ls -l -display the all the files inside the namenode.

hdfs dfs -ls / #It will list the files inside the hadoop

-------------------------------------- 
//POINTING TO THE RIGHT REPOSITORY TO INSTALL STUFF ensure package installation works properly inside Hadoop nodes(namenode) (apt-Advanced Package Tool):
echo "deb http://archive.debian.org/debian stretch main" > /etc/apt/sources.list
echo "deb http://archive.debian.org/debian-security stretch/updates main" >> /etc/apt/sources.list
echo 'Acquire::Check-Valid-Until "false";' > /etc/apt/apt.conf.d/99no-check-valid-until
apt update
apt (Advanced Package Tool) is a package manager used in Debian-based Linux systems to install, update, and manage software.
#INSTALLING NANO EDITOR:
apt update && apt install nano
#INSTALLING PYTHON3:
apt-get install python3 -o Acquire::Check-Valid-Until=false
apt list –installed  # This command lists all installed packages on your system

# Install Python3 and pip3
apt-get install python3-pip

# Verify Python3 and pip3 installation
python3 --version
pip3 –version

# Install the hdfs Python library
pip3 install hdfs

docker cp C:\Users\Deepak Acharya K\Downloads\wiki_1k_lines namenode:/deepak/  #to move the file from windows to the docker ie,linux

python3 /deepak /mapreduceMRJOB.py hdfs:///user/deepak/1k.txt --word the -r hadoop #to run it in hadoop
