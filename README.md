# Vue.js + Docker + Dokku (Automated Content Push)

## Getting Started
These instructions will guide you to start your vue js project directly deployed on the host you own so  you can start experimenting immediatelly and see the magic. 

### Prerequisites
You need npm,yarn and docker installed in order to be able to work in the project 
This project is build for the yarn package manager so choose option when you go through the  project setup

### Installing

A step by step series of examples that tell you how to get a development env running

```
chmod +x installer.sh
./installer.sh
? Project name (our-test-dokku-project) :[Enter project name here]
? Project description (A Vue.js project) :[Enter Description here or Press Enter]
?Author:[Enter Author or Press Enter]
? Vue build standalone
? Install vue-router? [Yes]
? Use ESLint to lint your code? [No]
? Set up unit tests [No]
? Setup e2e tests with Nightwatch? [No]
? Should we run `npm install` for you after the project has been created? (recommended) (Use arrow keys)
❯ Yes, use Yarn 
  Yes, use NPM 
....... Loading ..Be patient will take a bit to prepare everything.......

Would you like to generate a SSH-KEY?[Yes/[NO]]
Modify the keyname only or use your own path /Users/angjelothoma/.ssh/keyname?[/Users/angjelothoma/.ssh/modified-name]]
Enter a comment: [example@cool]
Passphrase: [empty]

//Let the script running and coninitue to the next step becase we will need the IP of the server that we be deploying on
//GO to vultr or digital ocean and create a server preferably at least 1gb RAM 
//Create an SSH key for the server by using the certificate that the script cated you before looks like(it is a bit long):
//ssh-rsa AAA........ ikiki 

What is ip addrress of the server?[Enter the server ip adress]
Provide Hostname:[Server IpAddress] or [Enter the domain name]
UserName : [dokku]

//It will copy the ssh key in the config (${HOME}.ssh/config) for dokku so it can push automatically)
if you dont have dokku installed on your VPS you can do that easily with the next 5 steps
 1) ssh to the container 
 2)wget https://raw.githubusercontent.com/dokku/dokku/v0.11.6/bootstrap.sh
 3)sudo DOKKU_TAG=v0.11.6 bash bootstrap.sh
 4)Open the browser and enter the VPS IP 
 5)Finish installation 

//back to our terminal in host the will push the code
cd ..

//you can modify the name from the script if you want 
cd our-test-project 

//Add files
git add . --all
//Lets commit our chanages 
git commit -m "initial"

//add remote reposiroy
git remote add [dokku(or whatevername you want)] [UserWeEnterBefore]@[YourVpsAdress]:node-js

// pussh changes
git push [RemoteHost Name] master

//Go to http://[YourServerIP]:80 and you will see your app is running (80 is the port that we exposed on the container)
//Anytime tou want push changes run git add. --all && git commit -m "initial" && git push [RemoteHostName] master
```
## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* https://medium.com/dirtyjs/how-to-deploy-vue-js-app-in-one-line-with-docker-digital-ocean-2338f03d406a (Automation of the setup provided )



