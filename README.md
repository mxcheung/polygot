# polygot

# install docker on ec2

https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html

```
 1010  sudo amazon-linux-extras install docker
 1011  sudo service docker start
 1012  sudo usermod -a -G docker ec2-user
```

# Step by Step

ssh -i "cheungm-mqtt.pem" ec2-user@ec2-54-79-195-173.ap-southeast-2.compute.amazonaws.com

git clone https://github.com/PrincessPolymath/polyglot.git

cd polygot
`docker run -i -t -p 8080:8080 synedra/polyglot`

# Links

https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html

https://github.com/PrincessPolymath/polyglot
