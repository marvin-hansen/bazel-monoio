# Replication


1) Install Bazelisk 

MacOS
```bash
brew install bazelisk
```

Ubuntu
```bash
sudo apt-get install bazelisk
```

2) Run build

```bash
cd cross_musl
bazel build //...
```

Note, Bazelisk will download the Bazel version specified in the .bazelversion file, and
Bazel will then analyze the build, download dependencies, and build the targets.