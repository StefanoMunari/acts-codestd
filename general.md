# GENERAL CODE STANDARDS  
## applicable to all programming languages  


* Each line of code must have a max length of 80 chars  
* Each function/procedure should have a max of 4 parameters  
* Each source file should contain a header with the following mandatory fields:  
	* author: a list of maintainers who have worked on this file. Please avoid
to report minor contribution to keep the
file slim and readable. The idea is [like this](https://github.com/torvalds/linux/blob/master/kernel/sched/fair.c).    
	* context: the package which contains the file  
	* purpose: briefly describes the source purpose  
	* interface: describes the interface of the file
* Each source file should contain a header with the following optional fields:  
	* dependencies: a list of related sources  
	* details: describe some implementation details related to the file (e.g. the memory layout)  
* Each class/function must be commented if it considered useful to understand 
the function/class purpose, otherwise (if the class/function is simple) 
comments are redundant and must be avoided to maintain readability   
* Each class/function should have a related test   
