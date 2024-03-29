# RTMP Streamer
## Get Started

```sh
docker run -d --name=rtmp1 --rm -it -p 1935:1935 registry.gitlab.com/inwinstack/team3/lab2/rtmp-nginx-streamer

docker exec -it rtmp1 /bin/bash

yt-dlp --list-formats https://youtu.be/S_bxc_AFUZU
yt-dlp --list-formats https://www.youtube.com/watch?v=obuN6LjaBlg
ffmpeg -re -i $(yt-dlp -f 300 -g https://youtu.be/S_bxc_AFUZU) -f flv -c:v copy -c:a copy rtmp://0.0.0.0/live/yt
ffmpeg -re -i $(yt-dlp -f 95 -g https://youtu.be/obuN6LjaBlg) -f flv -c:v copy -c:a copy rtmp://0.0.0.0/live/yt
```

## References

- [https://github.com/tiangolo/nginx-rtmp-docker](https://github.com/tiangolo/nginx-rtmp-docker)
- [https://gist.github.com/n3ksus/e973972f7a278d6bf19fa49fed86c109](https://gist.github.com/n3ksus/e973972f7a278d6bf19fa49fed86c109)

## License

This project is licensed under the terms of the MIT License.
