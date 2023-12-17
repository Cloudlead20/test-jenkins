
amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ls
Dockerfile  app.js  package.json

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ cat app.js
const http = require('http');

const server = http.createServer((req, res) => {
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end('testing, Node.js!\n');
});

const PORT = 5000;
server.listen(PORT, () => {
    console.log(`Server running at http://localhost:${PORT}/`);
});


amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker images
REPOSITORY                   TAG       IMAGE ID       CREATED        SIZE
node-app                     latest    8846d83431e6   19 hours ago   119MB
<none>                       <none>    7f5463d4c14b   19 hours ago   119MB
node-docker-app              latest    47207752c8b5   19 hours ago   119MB
<none>                       <none>    56522b5940c6   19 hours ago   119MB
muthuarumugam/test-jenkins   46        5b6dcc517073   22 hours ago   119MB
muthuarumugam/test-jenkins   44        8f9422fd2e27   38 hours ago   119MB
muthuarumugam/test-jenkins   43        916470dee7c0   38 hours ago   119MB
muthuarumugam/test-jenkins   42        3456b4db25ff   39 hours ago   119MB
muthuarumugam/test-jenkins   40        6243476c6efa   2 days ago     119MB
httpd                        latest    e499c02ff073   8 weeks ago    174MB
sample-app2                  latest    2889c1b556ff   2 months ago   953MB
<none>                       <none>    d677655049ef   2 months ago   953MB
<none>                       <none>    f1c97d11496a   2 months ago   953MB
sample-app                   latest    fe58166bb1de   2 months ago   953MB
muthuarumugam/test           v1        c5ba951f0029   3 months ago   953MB
my-node-app3                 latest    c5ba951f0029   3 months ago   953MB
project1                     latest    c5ba951f0029   3 months ago   953MB
project                      latest    c5ba951f0029   3 months ago   953MB
my-node-app2                 latest    3a7770da43d6   3 months ago   953MB
my-node-app1                 latest    a42ca5ca894d   3 months ago   953MB
my-node-app                  latest    4599d6669fa6   3 months ago   953MB
<none>                       <none>    4a11e9190530   3 months ago   953MB
hello-world                  latest    9c7a54a9a43c   7 months ago   13.3kB
hello-world                  linux     9c7a54a9a43c   7 months ago   13.3kB
infracloudio/csvserver       latest    8cb989ef80b5   2 years ago    237MB
learnitguide/busapp          latest    5274b804d827   4 years ago    1.24GB

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps
CONTAINER ID   IMAGE      COMMAND       CREATED        STATUS        PORTS                    NAMES
2258c95b37cd   node-app   "npm start"   19 hours ago   Up 19 hours   0.0.0.0:5000->5000/tcp   strange_kirch

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps -a
CONTAINER ID   IMAGE                           COMMAND                  CREATED        STATUS                     PORTS                    NAMES
4960717789c7   httpd                           "-p 81:80"               3 hours ago    Created                    80/tcp                   myhttpd1
2258c95b37cd   node-app                        "npm start"              19 hours ago   Up 19 hours                0.0.0.0:5000->5000/tcp   strange_kirch
c8a8122a0680   7f5463d4c14b                    "npm start"              19 hours ago   Exited (0) 19 hours ago                             vibrant_ride
2052f422bc5d   7f5463d4c14b                    "npm start"              19 hours ago   Exited (0) 19 hours ago                             frosty_mendeleev
604baf550e59   7f5463d4c14b                    "npm start"              19 hours ago   Exited (0) 19 hours ago                             elastic_meninsky
fca900f46654   56522b5940c6                    "docker-entrypoint.s…"   19 hours ago   Exited (1) 19 hours ago                             wizardly_lamarr
ed4a62901fd0   56522b5940c6                    "docker-entrypoint.s…"   19 hours ago   Exited (1) 19 hours ago                             xenodochial_goldstine
ea1ab6d8e7ce   5b6dcc517073                    "docker-entrypoint.s…"   19 hours ago   Exited (1) 19 hours ago                             sad_jennings
fa9adf0fee4f   5b6dcc517073                    "docker-entrypoint.s…"   19 hours ago   Exited (1) 19 hours ago                             zealous_kilby
4cf8c069d642   5b6dcc517073                    "docker-entrypoint.s…"   19 hours ago   Exited (1) 19 hours ago                             priceless_bartik
d5ba7f3477c3   5b6dcc517073                    "docker-entrypoint.s…"   19 hours ago   Exited (1) 19 hours ago                             cranky_wilson
fc01edfcfb49   muthuarumugam/test-jenkins:46   "docker-entrypoint.s…"   22 hours ago   Exited (1) 22 hours ago                             angry_swartz
426d22e75d22   infracloudio/csvserver:latest   "/csvserver/csvserver"   2 weeks ago    Exited (1) 2 weeks ago                              csvserver
8f729f31d58f   infracloudio/csvserver:latest   "/csvserver/csvserver"   2 weeks ago    Exited (1) 2 weeks ago                              stupefied_murdock
0f8965f222db   sample-app2                     "docker-entrypoint.s…"   4 weeks ago    Exited (255) 2 weeks ago   0.0.0.0:5000->5000/tcp   frosty_satoshi
dc426cddc2e9   sample-app2                     "docker-entrypoint.s…"   4 weeks ago    Exited (1) 4 weeks ago                              great_hawking
8361b65a488c   sample-app2                     "docker-entrypoint.s…"   4 weeks ago    Exited (1) 4 weeks ago                              gracious_lamport
918b805b8250   sample-app2                     "docker-entrypoint.s…"   4 weeks ago    Exited (255) 2 weeks ago   5000/tcp                 loving_moore
d2aeb1f2f2ed   learnitguide/busapp             "docker-entrypoint.s…"   6 weeks ago    Exited (9) 6 weeks ago                              funny_benz
e484124c10f2   sample-app2:latest              "docker-entrypoint.s…"   2 months ago   Exited (0) 2 months ago                             unruffled_jepsen
bfd15eab3792   d677655049ef                    "docker-entrypoint.s…"   2 months ago   Exited (0) 2 months ago                             wonderful_mirzakhani
4ed814ab2912   fe58166bb1de                    "docker-entrypoint.s…"   2 months ago   Exited (0) 2 months ago                             keen_austin
2a0ccad8455c   f1c97d11496a                    "docker-entrypoint.s…"   2 months ago   Exited (0) 2 months ago                             heuristic_heyrovsky
ec5872c0f2ba   f1c97d11496a                    "docker-entrypoint.s…"   2 months ago   Created                                             happy_heyrovsky
5e420aea0800   f1c97d11496a                    "docker-entrypoint.s…"   2 months ago   Created                                             inspiring_jepsen
e6be9a443d3a   sample-app                      "docker-entrypoint.s…"   2 months ago   Exited (0) 2 months ago                             silly_lalande
b1c7c51dc14f   sample-app                      "docker-entrypoint.s…"   2 months ago   Exited (0) 2 months ago                             festive_yonath
e808c2ad092c   muthuarumugam/test:v1           "docker-entrypoint.s…"   3 months ago   Exited (0) 3 months ago                             happy_williams
c44e5079e4d7   muthuarumugam/test:v1           "docker-entrypoint.s…"   3 months ago   Exited (0) 3 months ago                             tender_wilson
f9520fca1eda   muthuarumugam/test:v1           "docker-entrypoint.s…"   3 months ago   Exited (0) 3 months ago                             recursing_galois
117119bdb565   muthuarumugam/test:v1           "docker-entrypoint.s…"   3 months ago   Exited (0) 3 months ago                             upbeat_proskuriakova

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker stop 2258c95b37cd
2258c95b37cd

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker rm 2258c95b37cd
2258c95b37cd

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ cat app.js
const http = require('http');

const server = http.createServer((req, res) => {
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end('testing, Node.js!\n');
});

const PORT = 5000;
server.listen(PORT, () => {
    console.log(`Server running at http://localhost:${PORT}/`);
});


amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker build -t node-app2 .
#0 building with "default" instance using docker driver

#1 [internal] load .dockerignore
#1 transferring context: 2B 0.0s done
#1 DONE 0.1s

#2 [internal] load build definition from Dockerfile
#2 transferring dockerfile: 535B 0.0s done
#2 DONE 0.1s

#3 [internal] load metadata for docker.io/library/node:14-alpine
#3 ...

#4 [auth] library/node:pull token for registry-1.docker.io
#4 DONE 0.0s

#3 [internal] load metadata for docker.io/library/node:14-alpine
#3 DONE 2.0s

#5 [1/5] FROM docker.io/library/node:14-alpine@sha256:434215b487a329c9e867202ff89e704d3a75e554822e07f3e0c0f9e60
#5 DONE 0.0s

#6 [internal] load build context
#6 transferring context: 2.65kB 0.0s done
#6 DONE 0.1s

#7 [2/5] WORKDIR /app
#7 CACHED

#8 [3/5] COPY package*.json ./
#8 CACHED

#9 [4/5] RUN npm install
#9 CACHED

#10 [5/5] COPY . .
#10 DONE 0.1s

#11 exporting to image
#11 exporting layers 0.1s done
#11 writing image sha256:1d25417aae3bd52038b183056bb510a3f0e2a968787729a3dd25840fc7b574e9 0.0s done
#11 naming to docker.io/library/node-app2 0.0s done
#11 DONE 0.1s

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ls
Dockerfile  app.js  package.json

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ cat Dockerfile
# Use an official Node.js runtime as a base image
FROM node:14-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the current directory contents into the container at /app
COPY . .

# Make port 3000 available to the world outside this container
EXPOSE 5000

# Define the command to run the application
ENTRYPOINT ["npm", "start"]
amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker run -p 5000:5000 node-app2

> simple-node-docker@1.0.0 start /app
> node app.js

Server running at http://localhost:5000/

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps -a
CONTAINER ID   IMAGE                           COMMAND                  CREATED          STATUS                      PORTS                    NAMES
d8acdab5c131   node-app2                       "npm start"              46 seconds ago   Exited (0) 37 seconds ago                            unruffled_lederberg
4960717789c7   httpd                           "-p 81:80"               3 hours ago      Created                     80/tcp                   myhttpd1
c8a8122a0680   7f5463d4c14b                    "npm start"              19 hours ago     Exited (0) 19 hours ago                              vibrant_ride
2052f422bc5d   7f5463d4c14b                    "npm start"              19 hours ago     Exited (0) 19 hours ago                              frosty_mendeleev
604baf550e59   7f5463d4c14b                    "npm start"              19 hours ago     Exited (0) 19 hours ago                              elastic_meninsky
fca900f46654   56522b5940c6                    "docker-entrypoint.s…"   19 hours ago     Exited (1) 19 hours ago                              wizardly_lamarr
ed4a62901fd0   56522b5940c6                    "docker-entrypoint.s…"   19 hours ago     Exited (1) 19 hours ago                              xenodochial_goldstine
ea1ab6d8e7ce   5b6dcc517073                    "docker-entrypoint.s…"   19 hours ago     Exited (1) 19 hours ago                              sad_jennings
fa9adf0fee4f   5b6dcc517073                    "docker-entrypoint.s…"   19 hours ago     Exited (1) 19 hours ago                              zealous_kilby
4cf8c069d642   5b6dcc517073                    "docker-entrypoint.s…"   19 hours ago     Exited (1) 19 hours ago                              priceless_bartik
d5ba7f3477c3   5b6dcc517073                    "docker-entrypoint.s…"   19 hours ago     Exited (1) 19 hours ago                              cranky_wilson
fc01edfcfb49   muthuarumugam/test-jenkins:46   "docker-entrypoint.s…"   22 hours ago     Exited (1) 22 hours ago                              angry_swartz
426d22e75d22   infracloudio/csvserver:latest   "/csvserver/csvserver"   2 weeks ago      Exited (1) 2 weeks ago                               csvserver
8f729f31d58f   infracloudio/csvserver:latest   "/csvserver/csvserver"   2 weeks ago      Exited (1) 2 weeks ago                               stupefied_murdock
0f8965f222db   sample-app2                     "docker-entrypoint.s…"   4 weeks ago      Exited (255) 2 weeks ago    0.0.0.0:5000->5000/tcp   frosty_satoshi
dc426cddc2e9   sample-app2                     "docker-entrypoint.s…"   4 weeks ago      Exited (1) 4 weeks ago                               great_hawking
8361b65a488c   sample-app2                     "docker-entrypoint.s…"   4 weeks ago      Exited (1) 4 weeks ago                               gracious_lamport
918b805b8250   sample-app2                     "docker-entrypoint.s…"   4 weeks ago      Exited (255) 2 weeks ago    5000/tcp                 loving_moore
d2aeb1f2f2ed   learnitguide/busapp             "docker-entrypoint.s…"   6 weeks ago      Exited (9) 6 weeks ago                               funny_benz
e484124c10f2   sample-app2:latest              "docker-entrypoint.s…"   2 months ago     Exited (0) 2 months ago                              unruffled_jepsen
bfd15eab3792   d677655049ef                    "docker-entrypoint.s…"   2 months ago     Exited (0) 2 months ago                              wonderful_mirzakhani
4ed814ab2912   fe58166bb1de                    "docker-entrypoint.s…"   2 months ago     Exited (0) 2 months ago                              keen_austin
2a0ccad8455c   f1c97d11496a                    "docker-entrypoint.s…"   2 months ago     Exited (0) 2 months ago                              heuristic_heyrovsky
ec5872c0f2ba   f1c97d11496a                    "docker-entrypoint.s…"   2 months ago     Created                                              happy_heyrovsky
5e420aea0800   f1c97d11496a                    "docker-entrypoint.s…"   2 months ago     Created                                              inspiring_jepsen
e6be9a443d3a   sample-app                      "docker-entrypoint.s…"   2 months ago     Exited (0) 2 months ago                              silly_lalande
b1c7c51dc14f   sample-app                      "docker-entrypoint.s…"   2 months ago     Exited (0) 2 months ago                              festive_yonath
e808c2ad092c   muthuarumugam/test:v1           "docker-entrypoint.s…"   3 months ago     Exited (0) 3 months ago                              happy_williams
c44e5079e4d7   muthuarumugam/test:v1           "docker-entrypoint.s…"   3 months ago     Exited (0) 3 months ago                              tender_wilson
f9520fca1eda   muthuarumugam/test:v1           "docker-entrypoint.s…"   3 months ago     Exited (0) 3 months ago                              recursing_galois
117119bdb565   muthuarumugam/test:v1           "docker-entrypoint.s…"   3 months ago     Exited (0) 3 months ago                              upbeat_proskuriakova

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker run -p 5000:5000 node-app2

> simple-node-docker@1.0.0 start /app
> node app.js

Server running at http://localhost:5000/

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker run -d -p 5000:5000 node-app2
93dea03ab91153386db188af06bb8066f1444f1c60ec72b25a93a7fa0b1158bf

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker images
REPOSITORY                   TAG       IMAGE ID       CREATED         SIZE
node-app2                    latest    1d25417aae3b   7 minutes ago   119MB
node-app                     latest    8846d83431e6   19 hours ago    119MB
<none>                       <none>    7f5463d4c14b   19 hours ago    119MB
node-docker-app              latest    47207752c8b5   19 hours ago    119MB
<none>                       <none>    56522b5940c6   19 hours ago    119MB
muthuarumugam/test-jenkins   46        5b6dcc517073   22 hours ago    119MB
muthuarumugam/test-jenkins   44        8f9422fd2e27   38 hours ago    119MB
muthuarumugam/test-jenkins   43        916470dee7c0   39 hours ago    119MB
muthuarumugam/test-jenkins   42        3456b4db25ff   39 hours ago    119MB
muthuarumugam/test-jenkins   40        6243476c6efa   2 days ago      119MB
httpd                        latest    e499c02ff073   8 weeks ago     174MB
sample-app2                  latest    2889c1b556ff   2 months ago    953MB
<none>                       <none>    d677655049ef   2 months ago    953MB
<none>                       <none>    f1c97d11496a   2 months ago    953MB
sample-app                   latest    fe58166bb1de   2 months ago    953MB
my-node-app3                 latest    c5ba951f0029   3 months ago    953MB
project1                     latest    c5ba951f0029   3 months ago    953MB
project                      latest    c5ba951f0029   3 months ago    953MB
muthuarumugam/test           v1        c5ba951f0029   3 months ago    953MB
my-node-app2                 latest    3a7770da43d6   3 months ago    953MB
my-node-app1                 latest    a42ca5ca894d   3 months ago    953MB
my-node-app                  latest    4599d6669fa6   3 months ago    953MB
<none>                       <none>    4a11e9190530   3 months ago    953MB
hello-world                  latest    9c7a54a9a43c   7 months ago    13.3kB
hello-world                  linux     9c7a54a9a43c   7 months ago    13.3kB
infracloudio/csvserver       latest    8cb989ef80b5   2 years ago     237MB
learnitguide/busapp          latest    5274b804d827   4 years ago     1.24GB

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker rmi ^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker rmi node-app2
Error response from daemon: conflict: unable to remove repository reference "node-app2" (must force) - container 93dea03ab911 is using its referenced image 1d25417aae3b

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps
CONTAINER ID   IMAGE       COMMAND       CREATED         STATUS         PORTS                    NAMES
93dea03ab911   node-app2   "npm start"   6 minutes ago   Up 6 minutes   0.0.0.0:5000->5000/tcp   eloquent_almeida

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker stop 93dea03ab911
93dea03ab911

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker rm 93dea03ab911
93dea03ab911

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker rmi nodeapp-2
Error response from daemon: No such image: nodeapp-2:latest

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker rmi node-app2:latest
Error response from daemon: conflict: unable to remove repository reference "node-app2:latest" (must force) - container d8acdab5c131 is using its referenced image 1d25417aae3b

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker rmi node-app2:latest -f
Untagged: node-app2:latest
Deleted: sha256:1d25417aae3bd52038b183056bb510a3f0e2a968787729a3dd25840fc7b574e9

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker pull muthuarumugam/test-jenkins:44
44: Pulling from muthuarumugam/test-jenkins
Digest: sha256:c3200e06989de6299d39836e091cd5226c95a7b418cd133122a85db4385ccb77
Status: Image is up to date for muthuarumugam/test-jenkins:44
docker.io/muthuarumugam/test-jenkins:44

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview muthuarumugam/test-jenkins:44

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker run -d ^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker run -d muthuarumugam/test-jenkins:44
ee9b76cb6eb637851f356f16a11d5f71ca013f9f38001c89d814f388eb1f0e77

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker images
REPOSITORY                   TAG       IMAGE ID       CREATED        SIZE
node-app                     latest    8846d83431e6   19 hours ago   119MB
<none>                       <none>    7f5463d4c14b   19 hours ago   119MB
node-docker-app              latest    47207752c8b5   19 hours ago   119MB
<none>                       <none>    56522b5940c6   19 hours ago   119MB
muthuarumugam/test-jenkins   46        5b6dcc517073   22 hours ago   119MB
muthuarumugam/test-jenkins   44        8f9422fd2e27   39 hours ago   119MB
muthuarumugam/test-jenkins   43        916470dee7c0   39 hours ago   119MB
muthuarumugam/test-jenkins   42        3456b4db25ff   39 hours ago   119MB
muthuarumugam/test-jenkins   40        6243476c6efa   2 days ago     119MB
httpd                        latest    e499c02ff073   8 weeks ago    174MB
sample-app2                  latest    2889c1b556ff   2 months ago   953MB
<none>                       <none>    d677655049ef   2 months ago   953MB
<none>                       <none>    f1c97d11496a   2 months ago   953MB
sample-app                   latest    fe58166bb1de   2 months ago   953MB
my-node-app3                 latest    c5ba951f0029   3 months ago   953MB
project1                     latest    c5ba951f0029   3 months ago   953MB
project                      latest    c5ba951f0029   3 months ago   953MB
muthuarumugam/test           v1        c5ba951f0029   3 months ago   953MB
my-node-app2                 latest    3a7770da43d6   3 months ago   953MB
my-node-app1                 latest    a42ca5ca894d   3 months ago   953MB
my-node-app                  latest    4599d6669fa6   3 months ago   953MB
<none>                       <none>    4a11e9190530   3 months ago   953MB
hello-world                  latest    9c7a54a9a43c   7 months ago   13.3kB
hello-world                  linux     9c7a54a9a43c   7 months ago   13.3kB
infracloudio/csvserver       latest    8cb989ef80b5   2 years ago    237MB
learnitguide/busapp          latest    5274b804d827   4 years ago    1.24GB

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps
CONTAINER ID   IMAGE                           COMMAND                  CREATED         STATUS         PORTS      NAMES
ee9b76cb6eb6   muthuarumugam/test-jenkins:44   "docker-entrypoint.s…"   2 minutes ago   Up 2 minutes   3000/tcp   distracted_wiles
0a9cc0d246ae   muthuarumugam/test-jenkins:44   "docker-entrypoint.s…"   3 minutes ago   Up 3 minutes   3000/tcp   funny_wu

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker exec -it ^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker exec -it ee9b76cb6eb6 /bin/bash
the input device is not a TTY.  If you are using mintty, try prefixing the command with 'winpty'

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker logs ^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker logs ee9b76cb6eb6

> simple-node-docker@1.0.0 start /app
> node app.js

Server running at http://localhost:3000/

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ls
Dockerfile  app.js  package.json

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ cat Dockerfile
# Use an official Node.js runtime as a base image
FROM node:14-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the current directory contents into the container at /app
COPY . .

# Make port 3000 available to the world outside this container
EXPOSE 5000

# Define the command to run the application
ENTRYPOINT ["npm", "start"]
amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ls
Dockerfile  app.js  package.json

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ cat Dockerfile
# Use an official Node.js runtime as a base image
FROM node:14-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the current directory contents into the container at /app
COPY . .

# Make port 3000 available to the world outside this container
EXPOSE 5000

# Define the command to run the application
ENTRYPOINT ["npm", "start"]
amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker pull muthuarumugam/test-jenkins:44
44: Pulling from muthuarumugam/test-jenkins
Digest: sha256:c3200e06989de6299d39836e091cd5226c95a7b418cd133122a85db4385ccb77
Status: Image is up to date for muthuarumugam/test-jenkins:44
docker.io/muthuarumugam/test-jenkins:44

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview muthuarumugam/test-jenkins:44

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ls
Dockerfile  app.js  package.json

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker build -t anto-padhmanaban .
#0 building with "default" instance using docker driver

#1 [internal] load .dockerignore
#1 transferring context: 2B done
#1 DONE 0.1s

#2 [internal] load build definition from Dockerfile
#2 transferring dockerfile: 535B 0.0s done
#2 DONE 0.1s

#3 [internal] load metadata for docker.io/library/node:14-alpine
#3 ...

#4 [auth] library/node:pull token for registry-1.docker.io
#4 DONE 0.0s

#3 [internal] load metadata for docker.io/library/node:14-alpine
#3 DONE 2.1s

#5 [1/5] FROM docker.io/library/node:14-alpine@sha256:434215b487a329c9e867202ff89e704d3a75e554822e07f3e0c0f9e606121b33
#5 DONE 0.0s

#6 [internal] load build context
#6 transferring context: 2.33kB 0.0s done
#6 DONE 0.1s

#7 [2/5] WORKDIR /app
#7 CACHED

#8 [3/5] COPY package*.json ./
#8 CACHED

#9 [4/5] RUN npm install
#9 CACHED

#10 [5/5] COPY . .
#10 CACHED

#11 exporting to image
#11 exporting layers done
#11 writing image sha256:1d25417aae3bd52038b183056bb510a3f0e2a968787729a3dd25840fc7b574e9 done
#11 naming to docker.io/library/anto-padhmanaban 0.0s done
#11 DONE 0.0s

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker push muthuarumugam/anto-padhmanaban
Using default tag: latest
The push refers to repository [docker.io/muthuarumugam/anto-padhmanaban]
An image does not exist locally with the tag: muthuarumugam/anto-padhmanaban

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker push muthuarumugam/anto-padhmanaban:latest
The push refers to repository [docker.io/muthuarumugam/anto-padhmanaban]
An image does not exist locally with the tag: muthuarumugam/anto-padhmanaban

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker build -t anto-padhmanaban .
amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker run -d -p 5000:5000 anto-padhmanaban
c546c695eabfa9699637ef8fdcd2c1059c9c1a95448ef3fb91b1dd169b0eb0b6

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps
CONTAINER ID   IMAGE                           COMMAND                  CREATED             STATUS             PORTS                    NAMES
c546c695eabf   anto-padhmanaban                "npm start"              6 seconds ago       Up 4 seconds       0.0.0.0:5000->5000/tcp   xenodochial_carson
ee9b76cb6eb6   muthuarumugam/test-jenkins:44   "docker-entrypoint.s…"   About an hour ago   Up About an hour   3000/tcp                 distracted_wiles
0a9cc0d246ae   muthuarumugam/test-jenkins:44   "docker-entrypoint.s…"   About an hour ago   Up About an hour   3000/tcp                 funny_wu

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ^C
^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker logs
amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker logs amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker run -d -p 5000:5000 anto-padhmanaban
c546c695eabfa9699637ef8fdcd2c1059c9c1a95448ef3fb91b1dd169b0eb0b6
^C
^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker logs anto-padhmanaban
Error response from daemon: No such container: anto-padhmanaban

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps
CONTAINER ID   IMAGE                           COMMAND                  CREATED              STATUS              PORTS                    NAMES
c546c695eabf   anto-padhmanaban                "npm start"              About a minute ago   Up About a minute   0.0.0.0:5000->5000/tcp   xenodochial_carson
ee9b76cb6eb6   muthuarumugam/test-jenkins:44   "docker-entrypoint.s…"   About an hour ago    Up About an hour    3000/tcp                 distracted_wiles
0a9cc0d246ae   muthuarumugam/test-jenkins:44   "docker-entrypoint.s…"   About an hour ago    Up About an hour    3000/tcp                 funny_wu

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker logs ^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker logs c546c695eabf

> simple-node-docker@1.0.0 start /app
> node app.js

Server running at http://localhost:5000/

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ ^C

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker logs c546c695eabf

> simple-node-docker@1.0.0 start /app
> node app.js

Server running at http://localhost:5000/

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$ docker ps
CONTAINER ID   IMAGE                           COMMAND                  CREATED             STATUS             PORTS                    NAMES
c546c695eabf   anto-padhmanaban                "npm start"              2 minutes ago       Up 2 minutes       0.0.0.0:5000->5000/tcp   xenodochial_carson
ee9b76cb6eb6   muthuarumugam/test-jenkins:44   "docker-entrypoint.s…"   About an hour ago   Up About an hour   3000/tcp                 distracted_wiles
0a9cc0d246ae   muthuarumugam/test-jenkins:44   "docker-entrypoint.s…"   About an hour ago   Up About an hour   3000/tcp                 funny_wu

amrmu@DESKTOP-6N0V09O MINGW64 ~/Downloads/TEST (master)
$
