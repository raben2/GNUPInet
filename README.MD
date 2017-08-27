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
# alternatively you could download the tarball, for version 7.55.1-3:
# wget https://gnunet.org/sites/default/files/gnurl-7.55.1-3.tar.bz2
# wget https://gnunet.org/sites/default/files/gnurl-7.55.1-3.tar.bz2.sig
# gpg --verify-files https://gnunet.org/sites/default/files/gnurl-7.55.1-3.tar.bz2.sig
cd gnurl && \ 
./buildconf && \
# Please keep in mind that the configure flags could change, you are advised to read
# https://git.savannah.gnu.org/cgit/guix.git/tree/gnu/packages/gnunet.scm#n186 or
# the appropriate line in the file for starting with "(define-public gnurl" for
# the reference package.
./configure --prefix=/usr/local --enable-ipv6 --with-gnutls --without-libssh2 \
--without-libmetalink --without-winidn --without-librtmp --without-nghttp2 \
--without-nss --without-cyassl --without-polarssl --without-ssl \
--without-winssl --without-darwinssl --disable-sspi --disable-ntlm-wb \
--disable-ldap --disable-rtsp --disable-dict --disable-telnet \
--disable-tftp --disable-pop3 --disable-imap --disable-smtp --disable-gopher \
--disable-file --disable-ftp --disable-smb && \
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