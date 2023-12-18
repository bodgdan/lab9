## Run "instance_run.cmd" to run instance in aws

### SSH connect to instance or copy from aws :
ssh -i "path_to_your_keys.pem" -L 5566:127.0.0.1:2375 ubuntu@instance-ip

### For creating image
docker -H localhost:5566 build -t ng .

###  Launching a new container
docker -H localhost:5566 run -d -p 80:80 ng

### Checking our server in browser
http://instance-ip

### Displaying a list of images from our daemon running on localhost:5566 
docker -H localhost:5566 images

### Displaying a list of containers from our daemon running on localhost:5566
docker -H localhost:5566 ps

### Stoping our container by his ID
docker -H localhost:5566 stop <container ID>
