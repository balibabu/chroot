# inadyn

nadyn (In-a-Dyn) is a lightweight, open-source Dynamic DNS (DDNS) client designed to keep a domain name synced with a changing public IP address, commonly used in routers and Linux servers

## Install inadyn

```bash
apt install inadyn
```

## Create config

```bash
nano /etc/inadyn.conf
```

## Make sure no one is able to edit it except you

```bash
chmod 600 /etc/inadyn.conf
```

## Check if syntax is correct

```bash
inadyn --check-config -f /etc/inadyn.conf
```

## Check if its working with logs directly on the terminal

```bash
inadyn -n -l debug
```

## To run inadyn in the background

```bash
inadyn -n -l debug > /home/log/inadyn.log 2>&1 &
```

## To confirm if inadyn is working

```bash
ps aux | grep inadyn
```

## To force update

```bash
pkill -HUP inadyn
```
