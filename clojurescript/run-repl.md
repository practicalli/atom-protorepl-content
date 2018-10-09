# Run a ClojureScript Figwheel project from ProtoREPL

Open the ClojureScript project

Start a Clojure REPL as usual, eg `Ctrl-Alt-, L`

Once the REPL has started, then enter and evaluate the `start-figwheel!` function

```clojure
(figwheel-sidecar.repl-api/start-figwheel!)
```

![Atom ProtoREPL - ClojureScript REPL - start figwheel!](/images/atom-protorepl-clojurescript-start-figwheel-from-atom.png)


Figwheel will start and compile the ClojureScript project.  The application should now be running, eg. `http://localhost:3449`.

Finally connect to the ClojureScript REPL by evaluating `cljs-repl`

```clojure
(figwheel-sidecar.repl-api/cljs-repl)
```
![ClojureScript REPL - start cljs-repl](/images/atom-protorepl-clojurescript-figwheel-cljs-repl.png)
