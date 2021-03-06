Laravel Quick Start for OpenShift
========================

This git repository helps you get up and running quickly w/ a Laravel installation
on OpenShift. The backend database is MySQL and the database name is the
same as your application name (using $_ENV['OPENSHIFT_APP_NAME']).  You can call
your application by whatever name you want (the name of the database will always
match the application).


Running on OpenShift
----------------------------

Create an account at http://openshift.redhat.com/

Create a php application with mysql (you can call your application whatever you want)

    rhc app create laravel php-5.3 mysql-5.1

Add this upstream Laravel repo

    cd laravel
    git remote add upstream -m master git://github.com/nematix/laravel-openshift.git
    git pull -s recursive -X theirs upstream master
    # note that the git pull above can be used later to pull updates to Laravel
    
Then push the repo upstream

    git push

That's it, you can now checkout your application at:

    http://laravel-$yournamespace.rhcloud.com


