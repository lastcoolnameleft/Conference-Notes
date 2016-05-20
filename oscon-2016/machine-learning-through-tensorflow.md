# Diving into machine learning through TensorFlow

## Details:
* http://conferences.oreilly.com/oscon/open-source-us/public/schedule/detail/48997
* Slides: 
  * bit.ly/tensorflow-at-oscon
  * https://speakerdeck.com/juliaferraioli/diving-into-machine-learning-with-tensorflow
* Setup: https://github.com/amygdala/tensorflow-workshop
* Application: https://github.com/tensorflow/tensorflow
	

## Notes
* There was a lot of setup necessary for this class, which I unfortunately did not complete in time.  Google was very generous and helpful; however, the public WiFi was not, so I missed out on the beginning.
*	example:  Take reddit title data and interpret subreddit data
* word2vec:	Neural Net model for text classification
*	Convolutional Neural net
	*	convolution => filter across a matrix, filter learned to detect some feature (image processing to detect edges)
* TensorBoard - graph accuracy and learning info
*	Distributed Tensor Flow
	*	Kubernetes for distributed mgmt
	*	bit.ly/tensorflow-k8s
	*	http://kubernetes.io/
	* TensorFlow vs Google's DataFlow
		* Both OS now, DataFlow is going to Apache Incubator Project => Beam
		* DataFlow doesn't currently support iterative training model

## Other
* https://speakerdeck.com/juliaferraioli/in-the-name-of-whiskey
  * Whiskey!  ML!  Awesome!
  * Personal note:  I might want to investigate this using Barrelled and/or Distilld
*	https://blog.monkeylearn.com/a-gentle-guide-to-machine-learning/
