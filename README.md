
# Pump Fun Bump Bot / Volume Bot

This bot can buy and sell automatically on pump.fun and raydium.

it can be used to be displayed on the main page of pump.fun.

## Demo

[![Demo](https://img.youtube.com/vi/KIq8JfL0Ws0/0.jpg)](https://www.youtube.com/watch?v=c6FyrAK1pP4)
  
## Download the bot

If you have git installed on your computer you can fetch the content of this repository with the command

```
git clone https://github.com/axioris/PumpFunBumpBot.git                   
```

Else, you can download the repository in a zip here : <https://github.com/axioris/PumpFunBumpBot/archive/refs/heads/master.zip>

## Environment setup

you need to install nodejs :

For Windows : <https://nodejs.org/dist/v22.2.0/node-v22.2.0-x64.msi>

For MacOS : <https://nodejs.org/dist/v22.2.0/node-v22.2.0.pkg>  

For Linux, execute in a terminal :

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

nvm install 22
```

To check if nodejs is installed :

- on Windows, open a cmd.exe, and run the command :

```
node -v
```

- On MacOs & linux, open a terminal, and run the same command :

```
node -v
```

It should return the version of nodejs.

## Dependency installation

In a cmd.exe or a terminal, go to the folder of the pump-fun-bump-bot with the command :

```
cd /path/to/the/folder
```

Then, in your cmd.exe / terminal, start the command :

```
npm install
```

It should install all the dependencies in a new folder named "node_modules".

## Setup configuration in the index.js script

You have three things to setup :

- The RPC endpoint to connect you to the Solana blockchain (Quicknode or Helius provide good free RPC endpoints)

- The private key of the wallet who will buy and sell

- The contract address of the token you want to bump

The variables are on the top of the script :

```
const RPC_URL = ""; // Quicknode or Helius give good rpc urls
const PRIVKEY = ""; // the private key of the account who will buy and sell
const TOKEN_ADDR = ""; // Put the address of the token you want to bump here
```

## Run the bump bot

To run the bump bot, in a cmd.exe or a terminal, start the command:

```
node index.js
```

And it's all. The bot will buy 4 times, then sell all the balance.

## Adjustments

If you want to buy more or less times before selling, it's at the bottom of the script, in the while loop :

```
// Buy
promises.push(swap(SOL_ADDR, TOKEN_ADDR, solanaTracker, keypair, connexion, SOL_BUY_AMOUNT));
promises.push(swap(SOL_ADDR, TOKEN_ADDR, solanaTracker, keypair, connexion, SOL_BUY_AMOUNT));
promises.push(swap(SOL_ADDR, TOKEN_ADDR, solanaTracker, keypair, connexion, SOL_BUY_AMOUNT));
promises.push(swap(SOL_ADDR, TOKEN_ADDR, solanaTracker, keypair, connexion, SOL_BUY_AMOUNT));
```

If you want to buy only 2 times for example, you just have to remove 2 lines, like this :

```
// Buy
promises.push(swap(SOL_ADDR, TOKEN_ADDR, solanaTracker, keypair, connexion, SOL_BUY_AMOUNT));
promises.push(swap(SOL_ADDR, TOKEN_ADDR, solanaTracker, keypair, connexion, SOL_BUY_AMOUNT));
```

Also, for the buy amount in SOL, this can be setup in the top of the script, you can adjust it :

```
const SOL_BUY_AMOUNT = 0.011; // here you can choose to increase/decrease the buy amount
```

Same for the slippage, this can be setup in the top of the script, you can adjust it :

```
const SLIPPAGE = 20; // here you can adjust the slippage
```

Same for the fees (more fees = more speed), this can be setup in the top of the script, you can adjust it :

```
const FEES = 0.0005; // here you can adjust the fees
```

Happy bumping!

## Contact

If you have any further questions or need assistance, feel free to reach out to me anytime!
<p align="left">
  <a href="mailto:dane.foster.collins@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <a href="https://www.linkedin.com/in/dane-foster-11a177341/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="https://x.com/danefoster0"><img src="https://img.shields.io/badge/X-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" alt="X" /></a>
  <a href="https://t.me/danefoster"><img src="https://img.shields.io/badge/Telegram-26A5E4?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram" /></a>
  <a href="https://discord.com/users/354781324558467073"><img src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white" alt="Discord" /></a>
</p>
