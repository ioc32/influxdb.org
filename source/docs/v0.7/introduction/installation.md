# Installation

The easiest way to get started using InfluxDB is to head over to [play.influxdb.org](http://play.influxdb.org) where you can create a database and start writing data and exploring it through the administrative interface in seconds. There's no signup required. It's an open sandbox for you to play in.

Or, if you're ready to use InfluxDB in production, you may want to check out our [managed hosted InfluxDB offering](http://customers.influxdb.com).

## Ports
By default InfluxDB will use ports `8083`, `8086`, `8090`, and `8099`. Once you install you can change those ports and other options in the configuration file, which is located at either `/opt/influxdb/shared/config.toml` or `/usr/local/etc/influxdb.conf`

## Reporting

As of version 0.7.1, InfluxDB will report anonomous data once every 24 hours to m.influxdb.com. This includes the raft id (randomly generated 8 bytes), the InfluxDB version, the OS, and the architecture (amd64, ARM, etc). We don't log or track the IP Addresses that the reports are made from. This information is very helpful for our project. It lets us know how many servers are running out there in the world and, more importantly, which versions.

This is enabled by default. You can opt-out of this by editing the config file and setting `reporting-disabled = true`. However, we'd be very grateful if you keep it enabled.

## OS X

Installation on OS X 10.6 and higher is supported through [Homebrew](http://brew.sh/).

```
brew update
brew install influxdb
```

After you run the install you'll need to start up InfluxDB. The message gives you details on how to do this:

```
To have launchd start influxdb at login:
    ln -sfv /usr/local/opt/influxdb/*.plist ~/Library/LaunchAgents
Then to load influxdb now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.influxdb.plist
Or, if you don't want/need launchctl, you can just run:
    influxdb -config=/usr/local/etc/influxdb.conf
```

## Ubuntu & Debian
Debian users can install by downloading the package and installing it like this:

```bash
# for 64-bit systems
wget http://s3.amazonaws.com/influxdb/influxdb_latest_amd64.deb
sudo dpkg -i influxdb_latest_amd64.deb

# for 32-bit systems
wget http://s3.amazonaws.com/influxdb/influxdb_latest_i386.deb
sudo dpkg -i influxdb_latest_i386.deb
```

Then start the daemon by running:

```
sudo /etc/init.d/influxdb start
```

## RedHat & CentOS
RedHat and CentOS users can install by downloading and installing the rpm like this:

```bash
# for 64-bit systems
wget http://s3.amazonaws.com/influxdb/influxdb-latest-1.x86_64.rpm
sudo rpm -ivh influxdb-latest-1.x86_64.rpm

# for 32-bit systems
wget http://s3.amazonaws.com/influxdb/influxdb-latest-1.i686.rpm
sudo rpm -ivh influxdb-latest-1.i686.rpm
```

Then start the daemon by running:

```
sudo /etc/init.d/influxdb start
```

<a href="getting_started.html"><font size="6"><b>Now get started!</b></font></a>