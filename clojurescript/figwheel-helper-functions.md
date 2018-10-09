### Figwheel helper functions

Project created with Figwheel helper functions `user.clj` setup can evaluate the `fig-start` function in the Clojure REPL started in Atom.

```clojure
(fig-start)
```

![Atom ProtoREPL - ClojureScript REPL - fig-start](/images/atom-protorepl-clojurescript-repl-component--fig-start.png)


Now connect to the ClojureScript REPL

```clojure
(cljs-repl)
```

![ClojureScript REPL](/images/atom-protorepl-clojurescript-repl-component--cljs-start.png)


## Example helper functions

If you create a project with `lein-figwheel` it will contain a `user` namespace containing helper functions

Create a project using `lein new figwheel project-name`

In the file `dev/user.clj` you will find the following helper funcitons


```clojure
(defn fig-start
  "This starts the figwheel server and watch based auto-compiler."
  []
  ;; this call will only work are long as your :cljsbuild and
  ;; :figwheel configurations are at the top level of your project.clj
  ;; and are not spread across different lein profiles

  ;; otherwise you can pass a configuration into start-figwheel! manually
  (f/start-figwheel!))

(defn fig-stop
  "Stop the figwheel server and watch based auto-compiler."
  []
  (f/stop-figwheel!))

;; if you are in an nREPL environment you will need to make sure you
;; have setup piggieback for this to work
(defn cljs-repl
  "Launch a ClojureScript REPL that is connected to your build and host environment."
  []
  (f/cljs-repl))
```
