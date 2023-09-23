# lab-install-ruby

Steps to install ruby in Ubuntu.

Pre requirements: https://github.com/JulioCesarBehenckChaves/lab-install-pgadmin.git

### Sqlite, compilers

```bash
sudo apt-get install build-essential git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev -y
sudo apt-get install libssl-dev zlib1g-dev sqlite3 libsqlite3-dev -y
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install nodejs -y
```



sudo apt-get install build-essential git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev -y
sudo apt-get install libssl-dev zlib1g-dev sqlite3 libsqlite3-dev -y
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init - bash)"' >> ~/.bashrc
source ~/.bashrc
type rbenv


Ruby
rbenv install -l
rbenv install 3.2.0 -v
rbenv global 3.2.0
ruby -v
Gems
echo "gem: --no-document" > ~/.gemrc
gem install bundler
gem update --system 3.4.18
gem install bundler
gem env home


Rails
gem install rails -v 7.0.4
rbenv rehash
rails -v



References: https://www.vultr.com/docs/installing-ruby-on-rails-on-ubuntu-20-04/?utm_source=performance-max-latam&utm_medium=paidmedia&obility_id=17096555207&utm_adgroup=&utm_campaign=&utm_term=&utm_content=&gclid=CjwKCAjw5remBhBiEiwAxL2M9yrk0gGmMdPUp6yGgQcKH-mGcW4TcnemUHrcVvmecKP40O-TLleknhoCuFcQAvD_BwE#Prerequisites  and  https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-22-04
