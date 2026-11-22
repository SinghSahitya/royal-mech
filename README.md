# Mech Royale bot (`mechfight/1`)

Entry for the Builders Buildathon 2026 Mech Royale track: a compiled Go bot in a `FROM scratch` image.

## Build and check

```sh
docker build --platform linux/amd64 -t mech-bot .
python3 check/check.py --map-dir /arena -- docker run --rm -i --network none --cpus 1 --memory 512m \
  --read-only --tmpfs /tmp:rw,size=64m --user 65534:65534 -v "$PWD/arena:/arena:ro" mech-bot
```
