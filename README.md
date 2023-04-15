# Blockchain Based Certificate Specification
>Built using Ethereum on local blockchain setup and deployed on Rinkeby test network.

## Steps to set up local development environment

1. We need to Download and install xampp to run the PHP files.

   ```
   https://sourceforge.net/projects/xampp/
   ```

   > PHP is the most popular and widely-used server-side scripting language for web development. However, it requires a webserver to run even a locally developed webpage.There are various web server software for setting up our local webserver. Amongst them, PHP XAMPP is one of the most popular.

2. To start the local server.

   > Oncee you open the the Xampp Control Panel Window there will be a lot of options. First in the module name 'Apache' click start button and in the 'MYSQL' module click start again. Then click on the 'Admin' of the 'MySQL' module. After clicking on 'admin' you will see a webpage opening on the local brower.
  

  
3. Run The Code
   >Put all the files in an folder and copy the folder to "C:\xampp\htdocs". Then go to your brower and type "localhos/'Your folder Name'" and click enter. Like I put my file in an folder name 'example', So I go to any browser and type "localhost/example" .This will open the Webpage.

   ```bash
   npm run contract-deploy
   ```

> The above 2 steps need to be run everytime you are running the project.

### Setting local database
1. Find the file in the Database folder name 'bcertify'.
2. Open 'localhost/phpmyadmin/'. Then go to Databases -> Click on 'Create Database' -> Giver the database  name '' -> Click on the 'Import' button on the top bar -> Under the 'File to import' Section Click on Browse and Select the .SQL file-> Click 'Import'.
3. You can see all the tables and Data


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

