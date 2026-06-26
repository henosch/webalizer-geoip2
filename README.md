# webalizer-geoip2

Webalizer 2.23-08 with GeoIP2 support (libmaxminddb) and cleaned-up pie charts.

## Original

- **Author**: Bradford L. Barrett
- **Version**: 2.23-08
- **Source**: Debian Archive (`webalizer_2.23.08.orig.tar.gz`)
- **Original Homepage**: http://www.webalizer.org (currently unavailable)

## What was changed

| Commit | Description |
|--------|-------------|
| 1 | Original Webalizer 2.23-08 source code |
| 2 | `webalizer.c`: Replaced libGeoIP with libmaxminddb (GeoIP2) |
| 3 | `output.c`: Updated GeoIP lookup to MMDB API |
| 4 | `configure.in`: Use libmaxminddb instead of libGeoIP |
| 5 | `graphs.c`: Cleaned up pie charts (removed 3D shadow, text shadow, larger font) |

## Build

```bash
git clone https://github.com/henosch/webalizer-geoip2.git
cd webalizer-geoip2

sudo apt-get install build-essential libgd-dev libmaxminddb-dev libdb-dev libpng-dev libz-dev

autoreconf -fi
./configure --enable-geoip --enable-dns
make
sudo make install
```

## Configuration

In `/etc/webalizer/webalizer.conf`:

```
GeoIP yes
GeoIPDatabase /var/lib/GeoIP/GeoLite2-Country.mmdb
```

## License

GPL v2 (see `COPYING`)
