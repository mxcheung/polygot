# polygot

# Objectives
- Explore Perl Dancer and Mongo modules
- Docker ==>  Mongodb +  [Python| Perl | Ruby | Node]
- CRUD script ==> dancer-server.pl  and flask-server.py


# install docker on ec2

https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html

```
 1010  sudo amazon-linux-extras install docker
 1011  sudo service docker start
 1012  sudo usermod -a -G docker ec2-user
```

# run in docker
```
[ec2-user@ip-172-31-44-23 polyglot]$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS                    NAMES
e15a7542e498        synedra/polyglot    "/bin/bash"         6 minutes ago       Up 6 minutes        0.0.0.0:8080->8080/tcp   exciting_ganguly
[ec2-user@ip-172-31-44-23 polyglot]$ docker exec -it e15a7542e498 /bin/bash
===========================================================================================
=  Welcome to the Docker Container for the Polyglot Class                                 =
===========================================================================================
=   >> mongod                                                                             =
=   >> mongoimport --collection quotes --file quotes.json --jsonArray                     =
===========================================================================================
[ Polyglot Course: /opt/Chapter1 ] >>

```

# Mongodb start

```
[ec2-user@ip-172-31-19-190 ~]$ docker exec -it 5143d3b5dd3c /bin/bash
===========================================================================================
=  Welcome to the Docker Container for the Polyglot Class                                 =
===========================================================================================
=   >> mongod                                                                             =
=   >> mongoimport --collection quotes --file quotes.json --jsonArray                     =
===========================================================================================
[ Polyglot Course: /opt/Chapter1 ] >> /etc/init.d/mongodb start
 * Starting database mongodb                                                                                            [ OK ]
```

# Step by Step

ssh -i "cheungm-mqtt.pem" ec2-user@ec2-54-79-195-173.ap-southeast-2.compute.amazonaws.com

git clone https://github.com/PrincessPolymath/polyglot.git

cd polyglot

`docker run -i -t -p 8080:8080 synedra/polyglot`


# Test the website
```
[ Polyglot Course: /opt ] >> cd Chapter4
[ Polyglot Course: /opt/Chapter4/04_02 ] >> cd Start
[ Polyglot Course: /opt/Chapter4/04_02/Start ] >> ls
config.yml  dancer-server.pl
[ Polyglot Course: /opt/Chapter4/04_02/Start ] >> perl dancer-server.pl
>> Dancer 1.3202 server 31 listening on http://0.0.0.0:8080
== Entering the development dance floor ...
```

to see the welcome message
http://ec2-54-79-195-173.ap-southeast-2.compute.amazonaws.com:8080/

```
{
   "message" : "Hello from Perl and Dancer"
}
```
http://ec2-54-79-195-173.ap-southeast-2.compute.amazonaws.com:8080/api/quotes

http://ec2-13-210-167-124.ap-southeast-2.compute.amazonaws.com:8080/demo

# Cloud 9
To bypass docker install steps
Cloud 9 has docker already installed however by default cloud 9 has only 8 GB disk space.
Expand EBS volume to 20 GB and restart cloud 9

`docker run -i -t -p 8080:8080 synedra/polyglot`
/etc/init.d/mongodb start
mongoimport --collection quotes --file quotes.json --jsonArray    

Preview
```
https://16b302e3292c46759b9ada9ee894ff46.vfs.cloud9.ap-southeast-2.amazonaws.com/demo
```

# Links

https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html

https://github.com/PrincessPolymath/polyglot

https://hub.docker.com/r/synedra/polyglot/

https://github.com/PrincessPolymath/polyglot/blob/master/Chapter4/04_04/dancer-server.pl

https://github.com/PrincessPolymath/polyglot/blob/master/Chapter3/03_04/flask-server.py

https://cloudaffaire.com/how-to-install-git-in-aws-ec2-instance/
