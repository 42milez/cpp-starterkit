# Reliable UDP
![Travis (.org) branch](https://img.shields.io/travis/42milez/cpp-starterkit/master) ![Codecov branch](https://img.shields.io/codecov/c/gh/42milez/cpp-starterkit/master)

## Development
#### Build docker image
SSH key pair is required before building docker image.
```
ssh-keygen -t ed25519 -C "" -f docker/id_ed25519
docker-compose build
```

#### Start dev-server
Any files are not transferred to dev-server by default. If you use [CLion](https://www.jetbrains.com/clion/), you can deploy your project by following [the instruction](https://github.com/42milez/rudp/wiki/Remote-Debugging-with-CLion).
```
docker-compose up -d dev-server
```

#### Connect to dev-server via SSH
```
ssh root@localhost -p 2222 -i docker/id_ed25519
```

#### Run test
###### with code coverage:
```
docker-compose run --rm -e COVERAGE=ON test
```

###### with sanitizer:
- Address Sanitizer: `docker-compose run --rm -e ASAN=ON test`
- Leak Sanitizer: `docker-compose run --rm -e LSAN=ON test`
- Memory Sanitizer: `docker-compose run --rm -e MSAN=ON test`
- Thread Sanitizer: `docker-compose run --rm -e TSAN=ON test`
