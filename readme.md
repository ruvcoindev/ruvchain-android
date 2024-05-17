## build instructions

* install gomobile

```bash
go install golang.org/x/mobile/cmd/gomobile@latest
```

* build ruvchain-go for android:

```
git clone https://github.com/ruvcoindev/ruvchain-go /tmp/ruvchain-go
cd /tmp/ruvchain-go
./contrib/mobile/build -a
```

* clone ruvchain for android and copy over the built go library

```
git clone https://github.com/ruvcoindev/ruvchain-android /tmp/ruvchain-android
mkdir /tmp/ruvchain-android/app/libs
cp /tmp/ruvchain-go/ruvchain.aar /tmp/ruvchain-android/app/libs/
```

* build ruvchain-android

```
cd /tmp/ruvchain-android
./gradlew assembleRelease
```

note: you will need to use jdk-11 as jdk-16 `"doesn't work" ™`

on debian/ubuntu you can set which jdk used with the `JAVA_HOME` env var:
```
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64/
```
