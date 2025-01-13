[![OpenIPC logo][logo]][site_basic]


## Notes


### FFMPEG

```
# Send RTMP from file
ffmpeg -re -i test.mp4 -c:v libx264 -c:a aac -f flv rtmp://my.server.com:1935/openIPC/ffmpeg-test
```


### MAJESTIC

```
# Install current DEV version for T31 (Lite)
curl -L https://openipc.s3-eu-west-1.amazonaws.com/majestic.t31.lite.master.tar.bz2 -o - | bunzip2 | tar xf - -C /tmp
mv /tmp/*/majestic /usr/bin
```


### SYSTEM

```
# Check software versions and hardware
grep -e OPENIPC_VERSION /etc/os-release ; majestic -v ; diff /usr/bin/majestic /rom/usr/bin/majestic ; ipcinfo -cs
```

```
# Memory leak check
watch -n1 curl http://localhost/image.jpg -o /tmp/tmp
# and
watch -n1 free -h
```


[logo]: https://openipc.org/assets/openipc-logo-black.svg
[site_basic]: https://openipc.org
[telegram_en]: https://t.me/OpenIPC
