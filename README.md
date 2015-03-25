ore-yesware-gem
===============

This repository is a https://github.com/ruby-ore/ore template. We use it to
create new gems with some goodies in it we like to have.

### How to use it

Before you begin, you should have an empty repo created under the Yesware
account. This should be initialized with _nothing_ in it, not even the Readme
file. The git repo that ore will create for you will have the master branch on
it, and you will not be able to push (or have to do a force push) if the remote
repository is created with the default Readme in it.

Ensure you are using the ruby version and gemset you'd like to use for this
gem!.

    rvm current

If that isn't showing you what you like, run something like this:

    rvm use ruby-2.0.0-p598@yesware

Once you've got the right ruby version, make sure you've got ore installed. And
then install the yesware ore template that you'll be using when you mine your
gem.

    gem install ore
    ore install git://github.com/justin-yesware/ore-yesware-gem.git


Now you're ready to mine that gem. In the parent directory to where you want to
create your new gem:

    GEM=yeti_ore_testing
    # Update ore itself, to pick up the latest ore-yesware-gem
    ore update
    mine $GEM --markdown --yesware-gem --version=1.0.0 "--summary=Testing ore" "--description=Testing ore"
    cd $GEM
    git remote add origin git@github.com:justin-yesware/${GEM}.git
    git push -u origin master

