# Pu-239 Radiance

Radiance is a BitTorrent tracker written in C++ for the [Luminance](http://www.github.com/Empornium/Luminance) project. It supports requests over TCP and can track both IPv4 and IPv6 peers in a dual-stack mixed swarm. This has been modified to run with Pu-239 source code.

## Radiance Compile-time Dependencies

* [GCC/G++](http://gcc.gnu.org/) (4.7+ required; 4.8.1+ recommended)
* [LLVM/clang++](https://clang.llvm.org) (3.3+ required; 3.4+ recommended) (alternative to GCC/G++)
* [Boost](http://www.boost.org/) (1.55.0+ required)
* [libev](http://software.schmorp.de/pkg/libev.html) (required)
* [MySQL++](http://tangentsoft.net/mysql++/) (3.2.0+ required)
* [jemalloc](http://jemalloc.net) (optional, but highly recommended - preferred over tcmalloc)
* [TCMalloc](https://github.com/gperftools/gperftools) (optional)

Also required for debug builds:
* [gperftools](https://github.com/gperftools/gperftools) (CPU profiler bindings)

```
sudo apt-get install libboost-dev libboost-all-dev libev-dev libmysql++-dev libjemalloc-dev
```

### Standalone Installation

* Copy `radiance.example.conf` to `radiance.conf`

* Edit `radiance.conf` to your liking.

* Build Radiance:
```
autoreconf -i
./configure --with-jemalloc
make
sudo make install
```

## Running Radiance

### Run-time options:

* `-c <path/to/radiance.conf>` - Path to config file. If unspecified, the current working directory is used.
* `-d` - Fork to the background and run as a service daemon.
* `-v` - Print version string and exit.

### Signals

* `SIGHUP` - Reload config
* `SIGUSR1` - Reload torrent list, user list and client blacklist
