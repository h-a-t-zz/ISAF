# :ambulance: ISAF (إسعاف) :ambulance:
## Integrated Security Assessments for your dev Flow
```
    EeeiiiiiEEiiiii.....                                             
       \|/                                                           
        n______     .....iiiiiEEiiiieeEE                             
       :~;     :                  \|/                                
-----;``~'  +  ;------------ ______n --------------------------------
     `-@-----@-=            :     :~:                                
=========================== ;  +  '~``; =============================
                            =-@-----@-'                              
jgs------------------------------------------------------------------

                   DEVSECOPS IN A PYTHON NUTSHELL        
```
# Purpose
This project is a "simple" implementation of the DevSecOps Methodolgy, boiled down to the following pictures.
[![DevSecOps](https://insights.sei.cmu.edu/assets/content/CISecurityChecking2.png)](https://insights.sei.cmu.edu/sei_blog/2014/12/security-in-continuous-integration.html)

[![Try in PWD](DevSecOps.png)](https://medium.com/@H.A.T/how-to-implement-webs-hospital-b0d8b85389ce)

# Init
## Stack Deployement
You can quickly start this PoC (based on OpenFaaS) on Docker Swarm online using the community-run Docker playground: play-with-docker.com (PWD) by clicking the button below:  

[![Try in PWD](https://cdn.rawgit.com/play-with-docker/stacks/cff22438/assets/images/button.png)](http://labs.play-with-docker.com/?stack=https://gist.githubusercontent.com/h-a-t/eafbb19d7ce46c4ee4a541df018a5f37/raw/ed84dedd8fa08c7ac28bd41003b59c69a7b0593d/docker-compose.yml&stack_name=func)

Or use the docker-compose.yml file.

## Prerequisite
- Get your Jupyter token:

```bash
docker logs func_jupyter.1.shw9s15u6co3cuzp5sjft697t 2>&1 | grep token
10:03:07.492 LabApp] The Jupyter Notebook is running at:

http://[all ip addresses on your system]:8888/?token=54523693a4c91624e2efebd5e9dde139b784297e30089504

to login with a token: http://localhost:8888/?token=54523693a4c91624e2efebd5e9dde139b784297e30089504
```

- Install git, unzip, curl and faas-cli in the Jupyter container:

```bash
docker exec --user root -ti func_jupyter.1.shw9s15u6co3cuzp5sjft697t bash
root@b9300915e6ad:~# apt-get update && apt-get -y install unzip git curl
root@b9300915e6ad:~# curl -sSL https://cli.openfaas.com | sh # Not cool :/
```

- Change permissions of docker.sock for the sack of this PoC. :warning:Do not do this in a production environment:bomb:

```bash
chmod 777 /var/run/docker.sock
```
- Upload ISAF.iynb to your Jupyter instance, and press play! \o/
