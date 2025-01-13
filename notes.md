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

### SETTINGS

```
# Prepare RTMP
cli -s .video0.size 1280x720
cli -s .audio.enabled true
cli -s .audio.codec alaw
cli -s .audio.srate 8000
cli -s .audio.volume 1
cli -s .osd.enabled true
cli -s .osd.template "RTMP | %F %T %Z"
```


### SYSTEM

```
# Check software versions and hardware
grep -e OPENIPC_VERSION /etc/os-release ; /usr/bin/majestic -v ; /rom/usr/bin/majestic -v ; ipcinfo -cs
```

```
# Memory leak check
watch -n1 curl http://localhost/image.jpg -o /tmp/tmp
# and
watch -n1 free -h
```


### DEVICES

- http://172.19.32.219/image.jpg # SSC335D+OS02G10, RTMP, Veedo, Wowza
- http://172.17.32.218/image.jpg # T31L+SC2332, RTMP, Safel, SF VMS


[logo]: https://openipc.org/assets/openipc-logo-black.svg
[site_basic]: https://openipc.org
[telegram_en]: https://t.me/OpenIPC
