</p>

<p align="center">
  <img height="200" height="auto" src="https://user-images.githubusercontent.com/78480857/203496599-9794161f-671e-4a0c-b828-54685c7d59a7.jpg">
</p>

</p>

# STARKNET FULLNODE ON MAINNET

## Minimum requirements
- CPU : 4 Core
- RAM : 8 GB
- Disk: 100 GB

## Prequisites
- Join Starknet [Discord](https://discord.gg/qypnmzkhbc)
- Register on [Alchemy](https://alchemy.com/?r=zMzNTEyMTg0NjcxM)
- Follow official [Twitter](https://twitter.com/StarkWareLtd)

# 1. Register on Alchemy
if you already have an account on Alchemy, just create the new app for Ethereum Mainnet 
![alchem1](https://user-images.githubusercontent.com/78480857/203498088-2d6c34d0-7f00-4027-ae83-28d0ffce5dc2.png)
view the key
![alchem2](https://user-images.githubusercontent.com/78480857/203498110-0192073c-a170-4db3-86d5-0dbaccf1f5c3.png)
and copy your HTTPS
![alchem3](https://user-images.githubusercontent.com/78480857/203498143-8c7202d7-da56-4034-ad6a-5eeac69a2c0d.png)

*save your HTTPS for next step

# 2. Install Docker (Skip this step if you already installed before)
```
sudo apt update -y && sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt install docker-ce
```

# 3. Install Tools
```
sudo apt-get install -y pkg-config curl git build-essential libssl-dev screen
```

# 4. Clone the Repository
```
git clone --branch v0.4.0 https://github.com/eqlabs/pathfinder.git
```

# 5. Run Docker
```
mkdir -p $HOME/pathfinder
docker run -d \
  --rm \
  -p 9545:9545 \
  --user "$(id -u):$(id -g)" \
  -e RUST_LOG=info \
  --name starknet \
  -e PATHFINDER_ETHEREUM_API_URL="YOUR_HTTPS" \
  -v $HOME/pathfinder:/usr/share/pathfinder/data \
  eqlabs/pathfinder
  ```
  fill ```YOUR_HTTPS``` with your Alchemy HTTPS in [Step 1](https://github.com/DiscoverMyself/Starknet-Fullnode#1-register-on-alchemy)
  
  # 6. Create Screen for Log checker
  ```
  screen -R starknet
  ```
  and check the logs
  ```
  docker logs -f starknet
  ```
  
 (if you want to check the logs another time, just run command ```screen -Rd starknet```)
 
 All Set!
 
 you can wait the blocks synced.
 check recent block in [Explorer](https://voyager.online/)
 
 # 7. Send Proof
- Screenshoot your Alchemy Dashboard and post it on your twitter, and tag Starknet Twitter too
 ![alchemyss](https://user-images.githubusercontent.com/78480857/203500633-c57834b7-7359-479e-9e45-75d9fef1894e.png)

- Copy the link and post it in ```#✅｜full-node-success``` channel in their Discord with your IP address
![alchemfor](https://user-images.githubusercontent.com/78480857/203500781-8f9af40d-0ba6-4886-99e5-d684a69b8bd6.png)


Done ✅
