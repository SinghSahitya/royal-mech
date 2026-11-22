# Mech Royale bot (`mechfight/1`)

Entry for the Builders Buildathon 2026 Mech Royale track: a compiled Go bot in a `FROM scratch` image.

## Attribution

Built on the MIT-licensed "Apex-Go v3" engine by ahmad-ovh
(https://github.com/ahmad-ovh/Buildathon, commit `56e0f76`); see `LICENSE`.
Local tuning used the MIT-licensed simulator from https://github.com/anthonyteti/buildathon-mech-royale.

## Build and check

```sh
docker build --platform linux/amd64 -t mech-bot .
python3 check/check.py --map-dir /arena -- docker run --rm -i --network none --cpus 1 --memory 512m \
  --read-only --tmpfs /tmp:rw,size=64m --user 65534:65534 -v "$PWD/arena:/arena:ro" mech-bot
```
