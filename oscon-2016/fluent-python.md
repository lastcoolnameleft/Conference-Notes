# Fluent Python: Implementing intuitive and productive APIs

## Details:
* http://conferences.oreilly.com/oscon/open-source-us/public/schedule/detail/49831
* Luciano Ramalho (ThoughtWorks - Technical Principal)
* 1:30pm–5:00pm Tuesday, 05/17/2016
* https://github.com/fluentpython/pythonic-api
*	https://speakerdeck.com/ramalho/pythonic-apis

## Notes:
* Pythonic API's - Productivity through Consistency
* Author of Fluent Python
	* Translations:
	  * Russian:  Python, to the height of excellence
	  * Chinese:  Smooth Python
* Consistency is by design
	* Example:  LEGO
	* Duplo's and LEGO fit together
* Bothers people:  len is not consistent with Java, but Java is not consistent
* Guido = author of Python
* dunder = double Underscore __len__() => dunder len
* py.test is more "pythonic" than unittest
	* no need to import, define class, subclass
	* testcases are just functions
	* uses assert keyword instead of assert.equal...
* Pythonic api:
	* don't force you to write boilerplate, provide ready to use fcn's
* Hollywood principle:  Don't call us, we'll call you.
	* If you really need to work with Vectors & matrices, use NumPy
	* Bobby Woolf created paper that said you need to text representations.  One for UI to present to users "str()" and one for debug/logging "repr()"
	* You can add __mul__ / __rmul__ for Vector so that mul(Vector([1, 2]), 10) works and so does mul(10, Vector([1,2]))
	* Python zip is about zipper, not compression.  Creating tuples
		* efficient for large datastructures
	* list comprehension is stolen from Haskell lang (created by mathimeticans)
* If object is not hashable, cannot put into a set
* Use Doctest
	* https://docs.python.org/2/library/doctest.html
	* docstring has some conventions to enable it.  
		* must be first thing in module.	
		* "test the happy cases"  (because it's for documenting)
* functools:  https://docs.python.org/2/library/functools.html
* "Study well designed pkg from std lib and from PyPI"
* leverage first-class lang objects: fcn, modules, classes
	*	thinking about classes as objects makes Factory patterns redundant
	* Can do functional python or can also have classes that behave as functions (use call function)
