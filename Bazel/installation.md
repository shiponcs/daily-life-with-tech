It is preferred to use [`bazelisk`](https://github.com/bazelbuild/bazelisk) instead of using [`bazel`](https://github.com/bazelbuild/bazel) directly. `bazelisk` is a wrapper around `bazel` that allows you to use different versions of `bazel` accross different projects. 

#### Install Bazelisk in Ubuntu

1. **Delete/uninstall** `bazel` if you had installed it previously:
 ```sh
 sudo apt-get --purge remove bazel
 ```
If it doesn't work for you, sadly you have to remove it manually. You may follow this:
```sh
rm -rf ~/.cache/bazel~/.cache/bazel
rm -fr ~/.bazel ~/.bazelrc
```
And, also find the location of the binary file by `which bazel` and remove it. And, of course you can always run `find / -name bazel` and see what else you may need to remove. 

2. **Install** `bazelisk` in Ubuntu

The guide is [here](https://github.com/bazelbuild/bazelisk/blob/master/README.md#installation). But if you think the guide for Linux is not good for you, see mine:
- Download the appropiate file for your system from [here](https://github.com/bazelbuild/bazelisk/releases).
- Open terminal at the location you downloaded the file and
  ```sh
    chmod +x <downloaded-file-name>
    sudo mv bazelisk-linux-amd64 /usr/local/bin/bazel
  ```
  What we did above: we gave the file *execuation permission* and then moved it to `/usr/local/bin/` and renamed it to `bazel` so that you can call it as `bazel` directly from your terminal as, I hope, `/usr/local/bin/` is already present in your `PATH` variable. 
Don't believe me. Run: `bazel --version`
