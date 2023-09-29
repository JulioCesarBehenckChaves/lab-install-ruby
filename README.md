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

Validate the install:

```bash
node -v
```

It must returns something like:

dbadmin@ruby:~$ node -v
v18.17.1

### yarn

```bash
curl -fsSL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn -y
```

Validate the install

```bash
yarn -v
```

It must returns something like:

dbadmin@ruby:~$ yarn -v
1.22.19

### Rbenv - var environment

```bash
sudo apt install rbenv -y
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init - bash)"' >> ~/.bashrc
```

### Finally Ruby

We may find a lot od stable ruby version by typing "rbenv install -l". Rails requires Ruby 2.5.0 or greater.

```bash
rbenv install 3.0.2 -v
```

At the end you may see the following message:

Installed ruby-3.0.2 to /home/dbadmin/.rbenv/versions/3.0.2

#### Set global Ruby version.

```bash
rbenv global 3.0.2
```

Confirm installation with similar output.

```bahs
ruby -v
```

dbadmin@ruby:~$ ruby -v
ruby 3.0.2p107 (2021-07-07 revision 0db68f0233) [x86_64-linux]

#### Install Bundler using gem.

```bahs
gem install bundler
```

It must returns something like:

dbadmin@ruby:~$ gem install bundler
Fetching bundler-2.4.20.gem
Successfully installed bundler-2.4.20
Parsing documentation for bundler-2.4.20
Installing ri documentation for bundler-2.4.20
Done installing documentation for bundler after 0 seconds
1 gem installed

#### Install Rails using gem.

```bash
gem install rails
```

At the end you must see something like:

...
...
Parsing documentation for rails-7.0.8
Installing ri documentation for rails-7.0.8
Done installing documentation for zeitwerk, thor, method_source, concurrent-ruby, tzinfo, minitest, i18n, activesupport, nokogiri, crass, loofah, rails-html-sanitizer, rails-dom-testing, rack, rack-test, erubi, builder, actionview, actionpack, railties, mini_mime, marcel, activemodel, activerecord, globalid, activejob, activestorage, actiontext, mail, actionmailer, actionmailbox, websocket-extensions, websocket-driver, nio4r, actioncable, rails after 70 seconds
36 gems installed

Confirm successful installation.

```bash
rails -v
```

You must see something like:
dbadmin@ruby:~$ rails -v
Rails 7.0.8

### Creating a Test Application

Create a new Rails project.

```bash
cd ~
rails new hello-emap
cd hello-emap
```

At the end you must see something like:

...
...
Create controllers directory
      create  app/javascript/controllers
      create  app/javascript/controllers/index.js
      create  app/javascript/controllers/application.js
      create  app/javascript/controllers/hello_controller.js
Import Stimulus controllers
      append  app/javascript/application.js
Pin Stimulus
Appending: pin "@hotwired/stimulus", to: "stimulus.min.js", preload: true"
      append  config/importmap.rb
Appending: pin "@hotwired/stimulus-loading", to: "stimulus-loading.js", preload: true
      append  config/importmap.rb
Pin all controllers
Appending: pin_all_from "app/javascript/controllers", under: "controllers"
      append  config/importmap.rb

#### Start Rails server.

```bash
rails server --binding=0.0.0.0
```

Let it running at your console. You must see this:

Puma starting in single mode...
* Puma version: 5.6.7 (ruby 3.0.2-p107) ("Birdie's Version")
*  Min threads: 5
*  Max threads: 5
*  Environment: development
*  PID: 37614
* Listening on http://0.0.0.0:3000
Use Ctrl-C to stop

Now open a new ssh session to your server and open up the brave-browser.

Navigate to your server's IP address at port 3000 in a web browser:

```bash
http://127.0.0.1:3000
```

Na pasta, sobr app
rails s

na pasta app, criar tabela
rails g scaffold Book titulo:string description:string 

da erro ao acessar  /Book

rails db:migrate

também vê em /Books.json



References: https://www.vultr.com/docs/installing-ruby-on-rails-on-ubuntu-20-04/?utm_source=performance-max-latam&utm_medium=paidmedia&obility_id=17096555207&utm_adgroup=&utm_campaign=&utm_term=&utm_content=&gclid=CjwKCAjw5remBhBiEiwAxL2M9yrk0gGmMdPUp6yGgQcKH-mGcW4TcnemUHrcVvmecKP40O-TLleknhoCuFcQAvD_BwE#Prerequisites  and  https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-22-04

https://community.revelo.com.br/primeiros-passos-e-um-crud-com-ruby-on-rails/
