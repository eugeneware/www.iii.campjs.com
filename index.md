# campjs dokku server

This server lives at [http://www.iii.campjs.com](http://www.iii.campjs.com).

It uses [dokku](https://github.com/progrium/dokku), a light-weight mini
heroku running docker containers.

Here's a quick tutorial about how to get set up.

## How to add your keys to the dokku server

Supply your email as a paramete to the `add@iii.campjs.com` address, and use
the password `campjs` when prompted.

``` bash
$ cat ~/.ssh/id_rsa.pub | ssh add@iii.campjs.com your@email.com
add@iii.campjs.com's password:
Adding 'your@email.com' to dokku
b3:ac:58:b6:8d:d3:27:32:59:30:3e:ab:5c:0c:55:5b
```

## How to push to the dokku server

Example of how to push to dokku server:

``` bash
$ git clone git@github.com:heroku/node-js-sample.git
$ cd node-js-sample
$ git remote add dokku dokku@iii.campjs.com:node-js-sample
$ git push dokku master
Counting objects: 296, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (254/254), done.
Writing objects: 100% (296/296), 193.59 KiB, done.
Total 296 (delta 25), reused 276 (delta 13)
-----> Building node-js-app ...
Node.js app detected
-----> Resolving engine versions

... blah blah blah ...

-----> Application deployed:
  http://node-js-sample.iii.campjs.com
```

## How to remove your keys from the dokku server

Supply your email as a paramete to the `remove@iii.campjs.com` address, and use
the password `campjs` when prompted.

``` bash
$ ssh remove@iii.campjs.com your@email.com
remove@iii.campjs.com's password:
remove@iii.campjs.com's password:
Removing 'your@email.com' from dokku
```

## How to generate keys (if you don't have them)

For newbies who don't use ssh, here's the incantation to create your own key
pair:

``` bash
$ ssh-keygen -t rsa -C "your@email.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/yourusername/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in test_rsa.
Your public key has been saved in test_rsa.pub.
The key fingerprint is:
3b:1a:42:c2:54:b4:db:9c:10:a0:56:0d:5d:ec:73:32 your@email.com
```
