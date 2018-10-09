# ClojureScript

ClojureScript projects are supported by ProtoREPL.

ClojureScript projects using Figwheel can be run from ProtoREPL, or you can run `lein figwheel` externally and connect ProtoREPL via the nrepl port.

Projects created from the figwheel also contain a `user` namespace that contains helper functions for starting and stoping figwheel and the ClojureScript repl.

## ProtoREPL Dev Dependency

Any ClojureScript project should include the ProtoREPL dev dependency.

![ProtoREPL Dev Dependency](/images/atom-protorepl-clojurescript-dev-dependency-protorepl.png)
