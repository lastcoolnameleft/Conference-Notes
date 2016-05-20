# Building amazing cross-platform command-line apps in Go

# Details:
* http://conferences.oreilly.com/oscon/open-source-us/public/schedule/detail/49186
* Presenters:
  * Steve Francia (spf13-labs)
  * Ashley McNamara (Rackspace)
* http://www.slideshare.net/spf13
	

Notes:
* Human interface guidelines for CLI
  * commands are verbs
  * options are adverbs
  * tar is worst offender
  * zip/unzip is better
  * flags with flags?!
  * Example: ls (-S t -U are incompatable)
      * better appraoch --sort=[size,...]
  * git ls --stat --no-stat
      * better:  git ls --stat=false
	* when bill gates stole linux, he changed some things like \ and dir
  * start with unix philosophy 
		* simple, clear, composable, 
		* pronouncable!
		Ken Thomson & Dennis Richie
	* Subcommands - Good!
		* brew install, svn add
		* cli can do mutiple
		* brew install -v hugo == good  easy to stay
	* could think of command as robot for running cli app's
* Ashlie's takeaway from working with Go:
	* Con
	    * GOPATH is a PITA
			  * forces you to put code in github
			  * could use Atom
	* Pro
	  * built in web server.  (prod quality, unlike others)
		* don't need framework
		* statically types
		* strongly typed
		* compiled, memory managed, 
		* powerful concurrency built in
* Cool things:  
  * "single binary"
  * garbage collection
  * CSP
  * cross compilation (fast too)
  * has generics
  * building microservices
	* similar in design to Clojure but different in syntax
	* Designed by Google developers who wanted to prevent people from writing crappy c++/java
	* Easier to catch bad code
* Very opinionated.  e.g. Start brackets must be on same line
	* specific about spaces
* Does not have:  Classes, 
	* objects, complexity, types, 
* strings are immutable, sequence of characters, made up of individual bytes
	* multi-value types:  structs
	* Has arrays, but don't use them
		* slice vs array:  
			* slice = dynamic length
			* array = concrete type
			* slice = ref to array
			* array = you manage, slice Go managed.
			* always use slices (until you know better)
* map:  unordered key val
	* function = first class citizen in Go
		* can have multiple input values + multi return values
			* Python !!!  Doesn't actually return multiple values.  Combines into one and destructures		Common Lisp 
	* define other types, compose types
	* tooling
		* go fmt - formats code for you
		* go test - same test framework for all
	* shockingly fast compilation

# Lab
* https://github.com/spf13/tri
* "I designed by typing words how I'd want to use them"
	* "try list done" is bad because done is not a noun  "try list -p1"
	* https://github.com/spf13/cobra
	* Errors are not exceptional, they are just values
	* no exceptions in Go
	* PANIC:  Not an exception, use when you want to shut down program, need a stack trace
	* godoc -http=:6060
	  * http://localhost:6060/pkg/

# Links:
* https://github.com/mitchellh/go-homedir
* https://github.com/fatih/vim-go
* https://godoc.org/
		
