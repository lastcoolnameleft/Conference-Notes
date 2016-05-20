# Introduction to Clojure

# Details:
* http://conferences.oreilly.com/oscon/open-source-us/public/schedule/detail/50343
* Alex Miller (Cognitect)
*	http://cdn.cognitect.com/training/clojure-training-20160513.zip

# Notes:
*	4 major data structures:
	*	list (sequential, linked list)
	*	 vector (array)
	*	 map (dictionary/hash, key/value)
	*	 set
	*	all heterogeneous 
* Structure vs Semantics
	*	struct: list contains symbol contains numbers
	*	semantics :  list means invoke this.  
	*	First position is invokation.
		*	function, macro, special op (do, if, def)
* Everythign evaluates to itself, except for some exceptions
	*	lists are evaluate each argument and invokes the thing int he function position
		*	(+ x 2)
	*	quote turns off evaluation.  (quote (+ x 2))  returns (+ x 2) unevaluated
*	(use 'clojure.repl) ; brings in functions from that namespace
*	(doc +) ; returns doc string and arrity 
*	(find-doc "+")
*	(source not)
*	apply, let 

# Other:
* I bounced between this session and the TensorFlow one as I was very interested in ML and WiFi started behaving again.
