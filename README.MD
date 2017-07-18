GNUPInet GNUnet for your Raspi2/3
=================================

## Install GNUnet dependencies

### Build tools
```
apt-get install libtool automake autoconf autopoint gcc 
```

### Gnurl 
```
git clone https://git.taler.net/gnurl.git/ && \
cd gnurl && \ 
./buildconf && \
./configure --prefix=/usr/local && \
make && \
make install 
```
### GNUnet Dependencies

```
apt-get install libmicrohttpd10 libgcrypt11-dev libltdl-dev libunistring-dev gnutls-bin libidn11-dev libextractor3 gettext-tools openssl
```

### Database
```
apt-get install sqlite |mysql | pgsql 
```

### GNUnet
```
./bootstrap
export GNUNET_PREFIX=/usr/local/lib && \
addgroup gnunetdns && \
adduser --system --home "/var/lib/gnunet" --group gnunet --shell /bin/sh && \
./configure --prefix=$GNUNET_PREFIX/.. 
```