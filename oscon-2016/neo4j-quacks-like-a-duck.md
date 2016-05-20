# "Quacks like a Duck" - Neo4j graph database

# Details:
* Could not find session online.  Late entry?

# Notes:
*	@rustyrazorblade
*	graphx
*	graph frames
*	uses directed graph
*	Tinkerpop 3 - apache proj (incubating now)
*	Going to talk about gremlin
*	Query is flexibile, data model is extremely flexible.
*	OMG, the world is a graph!....but there are tradeoffs.
*	Tradeoffs:
	*	performance
	*		contact lists:  lots of overhead
	*	"big bird", colernal sanders, you and your cat "luther"
	*	if everything is connected, lots of overhead  
	*	if you just want to know people you are connected with.	"most problems can be solved with simple lists"
*	Great question:  "How do I know Patrick?"
	*	jon = g.v().has("nickname", "rustyrasorblade")
	*	jon.until(has("nickname":, PatrickMcFadin")), ... follow()?
	*	can get back six degrees of separation
*	It can find any path by using a graph.
*	can get intense answers with easy effort
*	Do you need a gdb?
	*	graph solves complex problems by utilizing power of relationships
		
