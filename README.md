# nft-rules

Miscellaneous nftables rules for testing

# Applying a configuration

```
sudo nft -f ./nftables-allow-all.conf
```

# Applying a chain from command line

```
nft list table inet filter

nft add chain inet filter rabbit3 { type filter hook input priority 1 \; policy accept \; }
nft add rule inet filter rabbit3 ip daddr 127.0.3.1 drop
nft add rule inet filter rabbit3 ip saddr 127.0.3.1 drop
nft add rule inet filter rabbit3 counter drop

nft delete chain inet filter rabbit3
```
