# Automate Wireguard configuration

Script to configure pointtopoint tunnel with [wireguard](https://www.wireguard.io/).

## Usage

``` bash
wg genkey | tee privatekey | wg pubkey > publickey
cat privatekey publickey
cp wireguard.sh-template wireguard.sh
# set your ips, privatekey and peers
$EDITOR wireguard.sh
```

``` bash
# install systemd service
ln -s $(readlink -f wireguard.service) /etc/systemd/system/wireguard.service
systemctl start wireguard
```

``` bash
# manual
./wireguard start
```
