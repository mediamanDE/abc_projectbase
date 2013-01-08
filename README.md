                        _ _                             
     _ __ ___   ___  __| (_) __ _ _ __ ___   __ _ _ __  
    | '_ ` _ \ / _ \/ _` | |/ _` | '_ ` _ \ / _` | '_ \ 
    | | | | | |  __/ (_| | | (_| | | | | | | (_| | | | |
    |_| |_| |_|\___|\__,_|_|\__,_|_| |_| |_|\__,_|_| |_|

# init project

    git clone https://scm.mediaman.de/git/${PRJNAME}
    cd ${PRJNAME}
    git submodule init
    git flow init
    git submodule update

# branches used
* typically development is made in develop branch
* releases are on master

see http://nvie.com/posts/a-successful-git-branching-model/ for details how projects are handled with git flow

# Build tools
* git flow
    * included in SourceTree Client in Mac
    * installable for other systems / console via https://github.com/nvie/gitflow
* http://abc.tools.qafoo.com/
    * part of this project in submodule "setup"
    * using ant

# help for build targets#
just run

    $ ant -p

and / or

    $ ant help

## common build targets

    ant test
    ant deploy
    ant bundle

## run local webserver

    ant run

or

    ant rundev

What is needed:
* ruby
    * http://www.ruby-lang.org/de/downloads/
* compass
    * gem install compass
* PHP 5.4
    * http://www.zend.com/en/products/server-ce/downloads

# common problems

## Problem during build

    build.xml:7: The following error occurred while executing this line:
    can't add target -commons:validate:before~hooked to extension-point -validate:before~hook because the extension-point is unknown.

is caused by wrong ant version, try with Ant 1.8.2 or above!

# why (not) using …

see discussion on https://wiki.mediaman.de/x/1wABAg

## ABC - Ant Build Commons
[http://abc.tools.qafoo.com]

because many guys know ant and are familiar in using ant, nevertheless ant is not as "cool" as other tools

## composer
[http://getcomposer.org/]

doesn't fit as a basic builder... might be used in projects as part of the (PHP)building process but not useful for
JS/CSS/HTML5 only projects (e.g. compass is not available as dependency in https://packagist.org/)

newest ABC supports composer! So just add your composer.json!

## yeoman.io
[http://yeoman.io]

"cool" but doesn't work on windows at the moment. also this tool will fit the JS/CSS part but no PHP part... so we still need some "wrapper"

perhaps we will use this in the future

## (Twitter) bower
[http://twitter.github.com/bower/]

well known, will fit to some tasks.. but still needs to be integrated to the context or needs to run manually (what's bad for new developers)
