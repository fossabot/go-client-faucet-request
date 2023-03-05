 [![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger) [![Go version][go-badge]][go-url] [![HitCount](https://hits.dwyl.com/whonion//go-client-faucet-request.svg)](https://hits.dwyl.com/whonion/go-client-faucet-request)
# Faucet-client for send multi-request to server using proxy</br>
Implementation with go-routines and without
## Package description:
 - main.go - main package to run or build (sequential proxy request sending)
 - go-routine.go - multi-send requests with go-routine(in testing stage)
 - proxy.go - package for getting a proxy list from a remote site(in testing stage)
 ## Description of required files:
 - proxy.txt - proxy list file in the protocol://ip:port@login@pass format
 - createwallets.sh  - batch generator of wallets with output of 'addresses.txt' file
 - addresses.txt - wallet's list for sending curl requests to target faucet's url
 - agents.txt - list of user-agents

## How to run with shell(without build) :
```sh
ver="1.20" && \
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz" && \
sudo rm -rf /usr/local/go && \
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz" && \
rm "go$ver.linux-amd64.tar.gz" && \
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile && \
source $HOME/.bash_profile && \
go version \
sudo apt-get install tmux \
tmux new -s go_faucet
```
```sh
git clone https://github.com/whonion/go-client-faucet-request.git \
cd go-client-faucet-request \
#make the file 'generatewallets.sh' executable
chmod +x createwallets.sh \
# generate wallet addresses for the Tendermint node
./createwallets.sh \
# add proxy to proxy.txt
go run  main.go \
```
```sh
# or run with goroutine
go run  go-routine.go
```
[go-badge]: https://img.shields.io/badge/go-1.20-blue.svg
[go-url]: https://go.dev
