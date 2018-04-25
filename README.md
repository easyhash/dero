# Daemon
```bash
docker run --name DeroDaemon --volume daemon:/daemon/data easyhash/dero:latest /daemon/dero_linux_amd64/derod-linux-amd64 --data-dir=/daemon/data --rpc-bind=0.0.0.0:18081
```

# Wallet
```bash
docker run --name DeroWallet --volume wallet:/daemon/data --link DeroDaemon:daemon easyhash/dero:latest /daemon/dero_linux_amd64/dero-wallet-cli-linux-amd64 --daemon-address=daemon:18081 --wallet-file=data/dero.wallet --rpc-server --rpc-bind=0.0.0.0:18082 --prompt '<wallet password>'
```