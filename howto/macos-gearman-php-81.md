# Setting up gearman with PHP 8.1 on a mac with Homebrew

1. install homebrew - https://brew.sh/
2. install gearmand with homebrew
```
brew install gearman
```
3. grab the latest pecl gearman, build it and install the extension
```
git clone https://github.com/php/pecl-networking-gearman
cd pecl-networking-gearman
phpize
./configure --with-gearman=$(brew --prefix gearman)
make && make test
make install
echo "extension=gearman.so" >> /opt/homebrew/etc/php/8.1/php.ini
```
4. check if the extension is enabled
```
php -i | grep gearman
```
