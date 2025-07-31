Set up the following fix tool on Windows:

```toml
[fix.tools.a]
command = ["a/script.bat"]
patterns = ["f"]
```

If you execute `jj fix` from the root:

```command
$ jj fix
f:
 hello from the nested script
```

But if you change into the `a` directory and run `jj fix` again, it runs the
script in `a/a/script.bat` instead:

```command
$ cd a
$ jj fix
..\f:
 hello from the double nested script
$ pwd
