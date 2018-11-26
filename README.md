# easy_switch
easy switch related rails engine git repos

**Dependencies on MacOS** :
```
$ brew install grep --with-default-names 
```


**Usages**:
```bash
$ cat FooProject/Gemfile
gem 'FooEngine', path:  '../somewhere/Foo'
gem 'BarEngine', path: '../Bar'
 ...
```

```bash
$ ./hook_setup ~/FooProject
Done...

$ cd FooProject
$ git checkout testing
Switched to branch 'testing'
BarEngine => testing
FooEngine => testing

$ SKIP=1 git checkout -
Switched to branch 'master'
# nothing happen to engines
```

**Error tolerance**

```
$ cd BarEngine
$ git checkout testing
error: Your local changes to the following files would be overwritten by checkout:
....
$ cd ../FooProject
$ git checkout testing
Switched to branch 'testing'
BarEngine => FAIL, repo not clean"
FooEngine => testing







