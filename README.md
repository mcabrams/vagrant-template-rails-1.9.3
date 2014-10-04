Vagrant Box for Ruby 1.9.3 Rails App Setup
------

- Install vagrant and virtualbox.
- Run `vagrant plugin install vagrant-vbguest` and `vagrant plugin install vagrant-librarian-chef`
- Run `vagrant up` from directory with `Vagrantfile`, _you may need to adjust forwarded port in Vagrantfile if there's a conflict_.
- Run `vagrant ssh`
- Change to /vagrant dir: `cd /vagrant`
- Run `bundle`
- Run `rbenv rehash`
- Run `psql -U postgres -h localhost`, ensure you have access via that command
- Run `rake db:create db:migrate db:seed`
- Run `psql -U postgres -h localhost`, ensure `todo_development` and `todo_test` are created
- Run `rails s`
- Hit on `localhost:3333`

- If you continue to see errors about guest addition mismatch between host and guest, go ahead and run `sudo ln -s /opt/VBoxGuestAdditions-4.3.10/lib/VBoxGuestAdditions /usr/lib/VBoxGuestAdditions`

You should now be setup.
