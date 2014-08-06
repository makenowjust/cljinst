#cljinst

Clojure Installer

##install

cljinst requires only `git` and `curl`. You have installed, you can use one liner to install cljinst:

```bash
$ curl -L git.io/cljinst | bash -s setup
```

Finish to install, please append following line to `.bashrc` etc.

```bash
export PATH=$HOME/.cljinst:$PATH
```

##examples

Show the list of available versions.

```bash
$ cljinst list-remote
...
1.6.0
```

Install Clojure 1.6.0.

```bash
$ cljinst install 1.6.0
```

Show the list of installed versions.

```bash
$ cljinst list
1.6.0
```

Run Clojure.

```bash
$ clojure
Clojure 1.6.0
user=> (println '(hello world))
(hello world)
nil
user=> (java.lang.System/exit 0)
```

Uninstall Clojure 1.6.0.

```bash
$ cljinst uninstall 1.6.0
```

Specify Clojure version to run.

```bash
$ cljinst install 1.5.1
$ CLOJURE_VERSION=1.5.1 clojure
Clojure 1.5.1
user=>
```

Update myself.

```bash
$ cljinst self-update
```

Show version.

```bash
$ cljinst version
0.1.2
```

Show help.

```bash
$ cljinst help
Usage:
  cljinst [-vd] <subcommand> [options...]

Subcommands:
  version      - Show cljinst's version
  help         - Show this help
  list         - List of installed clojure versions
  list-remote  - List of available clojure versions
  install      - Install specified version clojure
  uninstall    - Uninstall specified version clojure
  setup        - Set up myself
  self-update  - Update myself

Global Options:
  -v/--verbose - Display running commands
  -d/--dryrun  - Display commands, but not run
```

##configurations

###`$CLJINST_ROOT`

It is cljinst's root directory. cljinst is installed to it and install clojures to it.

default: `$HOME/.cljinst`

###`$CLJINST_REPO`

It is cljinst's repository. It is used in `cljinst setup`, so you can use it for testing and debugging.

default: `https://github.com/MakeNowJust/cljinst`

###`$CLJINST_CLOJURE_URL`

It is an URL of clojure's maven repository. If this server down, you can change this value.

default: `http://central.maven.org/maven2/org/clojure/clojure/`

###`$CLOJURE_VERSION`

It is clojure's version to run. If it is empty, its value is most large version.

default: `` (empty)

##What is `init.clj`

`$CLJINST_ROOT/init.clj` is a Clojure source file to load with running `clojure` automatically.
It was registered in `.gitignore`, so you can append and rewrite freely.

##license

cljinst is released under the MIT License, please look `LICENSE` file.
