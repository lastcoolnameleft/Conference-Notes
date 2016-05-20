# A data-streaming architecture with Apache Flink

## Details:
* http://conferences.oreilly.com/oscon/open-source-us/public/schedule/detail/49068
* Jamie Grier (data Artisans)	Director of App Eng

## Notes:
*	stateful stream processing
*	windowed computation over streams
* Robust time handling (event time vs processing time)
* Robust Failure handling, planned downtime handing, re-processing
*	What is it?  
	*	OS platform for distributed stream and batch data prcoessing
*	Stream processing:
	*	Data stream ->>  your code ->> data stream
*	Stateful stream processing
	*	Data stream ->>  your code ->> data stream
	  *	-also has state (counting, aggregation)
	* In flink, State is FCS and managed in Flink
* Event time vs processing time
	* Demo showed sawtooth data (0, 1) and sine wave. 
	*	"if you sum the sine wave over 1 sec, what should be the res?"  0
	*	Demo showed errors where =0
	*	Changed to sum over processing time.  Everything is 0
