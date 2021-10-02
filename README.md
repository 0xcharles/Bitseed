# Updating Bitseed to Bitcoin Core 0.21.1 

Updating your Bitseed server to may disable some functionalities from your original Bitseed.
The below steps are shared without any warranty. Expect the settings section of your bitseed to break after the upgrade.
The full node works fine months after the upgrade.

## Instructions

Use [Putty](https://www.putty.org/) to connect to your Bitseed server.

Pro tip: To paste on Putty= Shift+insert

## Step 1 : Download the latest version of Bitcoin Core.

```
wget https://bitcoin.org/bin/bitcoin-core-0.21.1/bitcoin-0.21.1-x86_64-linux-gnu.tar.gz
```
```
wget https://bitcoin.org/bin/bitcoin-core-0.21.1/SHA256SUMS.asc
```
```
sha256sum --ignore-missing --check SHA256SUMS.asc
```
```
tar xzf bitcoin-0.21.1-x86_64-linux-gnu.tar.gz
```
```
cd bitcoin-0.21.1
```
```
cd bin
```
```
sudo install -m 0755 -o root -g root -t /usr/local/bin *
```
```
bitcoind --daemon
```
In case you want to restart bitcoin, stop it first, before restarting it. It may take up to 20 minutes to rescan the blocks. Most of the time daemon restart take less than a minute.
```
bitcoin-cli stop
