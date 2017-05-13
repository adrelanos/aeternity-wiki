# Blockchain no longer syncing? #

Perhaps the testnet was reset? Try deleting folder _/deps/pink_hash_ in your _testnet_ folder.

([source](https://github.com/aeternity/testnet/issues/41))

# System Requirements #

Erlang (version >= 18)

Ubuntu (version >=16) (Windows coming soon) Or Mac OS

# Building from Source #

## For Ubuntu
Make sure that that you are running Ubuntu 16 or later:

(earlier versions of ubuntu requires manually installing the latest version of erlang, because the package manager installs an old version)

Use this command to check your version number
```
lsb_release -a
```

Make sure that your system is up-to-date:
```
sudo apt-get update
```
and
```
sudo apt-get upgrade
```

For Ubuntu, install following dependencies:

```
sudo apt-get install erlang libncurses5-dev libssl-dev unixodbc-dev g++ git erlang-base-hipe
```

Next, download æternity Testnet. Optionally you can run next steps with a non-root user, for better security.

```
git clone https://github.com/aeternity/testnet.git
```
Now you can go into the directory, and compile the æternity testnet.

```
cd testnet/
sh install.sh
```

Now you can run your node. with ```sh start.sh```


## For Mac

First install brew, a package manager for OSX.

https://brew.sh/


Next install erlang and rebar, the package manager for erlang
```
brew install erlang
brew install rebar
```

now use rebar to get and compile æternity:

```
rebar get
rebar get-deps
rebar compile
```

Now you can run your node with ```sh start.sh```

# What if my question isn't answered here? # 

Visit our [Slack](http://slack.aeternity.com/) or [Gitter](https://gitter.im/aeternity/Lobby) channels.