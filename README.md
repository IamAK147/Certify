# Blockchain Based Certificate Specification
>Built using Ethereum on local blockchain setup and deployed on Rinkeby test network.

## Steps to set up local development environment

1. We need to Download and install xampp to run the PHP files.

   ```
   https://sourceforge.net/projects/xampp/
   ```

   > PHP is the most popular and widely-used server-side scripting language for web development. However, it requires a webserver to run even a locally developed webpage.There are various web server software for setting up our local webserver. Amongst them, PHP XAMPP is one of the most popular.

1. To start the local server.

 > Oncee you open the the Xampp Control Panel Window there will be a lot of options. First in the module name 'Apache' click start button and in the 'MYSQL' module click start again. Then click on the 'Admin' of the 'MySQL' module. After clicking on 'admin' you will see a webpage opening on the local brower.
  

  
3.Run The Code
>put all the files in an folder and copy the folder to "C:\xampp\htdocs". Then go to your brower and type "localhos/'Your folder Name'" and click enter. This will open the webpage.

   ```bash
   npm run contract-deploy
   ```

> The above 2 steps need to be run everytime you are running the project.

### Setting local database

> MongoDB server should be running as a background Process

1. Open mongo in terminal using command `mongo`

1. Then change the db using command

   ```bash
   use certification
   ```

1. Then set DB user and password with the following command

   ```javascript
   db.createUser({
     user: "<YOUR USER NAME>",
     pwd: "<YOUR USER PASSWORD>",
     roles: [{ role: "dbOwner", db: "certification" }]
   });
   ```

1. Include these username and password in the `.env` file.

### Now we can start the server

```bash
npm start
```

## Deploying Smart Contract

The contract can be deployed in any test networks. We are using Rinkeby test network with help of truffle.

1. First of all we need to have a metamask account. When we create an account in metamask a _mnemonic_ is given to us. [You can read how to get a mnemonic here.](https://support.dex.top/hc/en-us/articles/360004125614-How-to-Create-Mnemonic-Phrase-with-MetaMask-)

1. After that create a project in [Infura](https://infura.io). This will help us to use rinkeby network through infura.

1. You will get an endpoint like this `https://rinkeby.infura.io/yourapikey`.

1. Create a `.env` file in root directory and paste the previously genrated mnemonic and the endpoint URL in that. An example is also provided in [.env.example](./.env.example) file.

   > For running in development environment and to use local blockchain network, use the LOCAL_ENDPOINT variable and replace the URL with your own local URL (These default values are filled already and shouldn't be changed unless until RPC server running on different port)

1. Now you can deploy the smart contract using a single command:

   ```BASH
   npm run deploy
   ```

1. You will get a contract address of newly generated contract. Save this for further uses.

## Testing app

To test the app run the command `truffle test`. RPC server should be running to run the tests.

## Useful reads

- [Some instructions and commands for debugging in Truffle Console](./instructions/COMMANDS.md)

## Youtube Video for better understanding of the project

[![youtube-picture](https://img.youtube.com/vi/pByqlMCx7Bk/maxresdefault.jpg)](https://www.youtube.com/watch?v=pByqlMCx7Bk)

---

| Developers                                             |                                                               |
| ------------------------------------------------------ | ------------------------------------------------------------- |
| [Saurabh Thakur](https://github.com/thakursaurabh1998) | ![st](https://avatars0.githubusercontent.com/u/18613564?s=50) |
