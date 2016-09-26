# GENERAL
* Each line of code must have a max length of 80 chars  
* Each function/procedure can have a max of 4 parameters  
* Each source file must contain a header with the following fields:  
  * description: briefly describes the source purpose  
  * see: a list of related sources  
  * mantainer: a list of mantainers that contributes to the source with 
the contribution description. Please avoid to report minor contribution to keep the
file slim and readable. The idea is [like this](https://github.com/torvalds/linux/blob/master/kernel/sched/fair.c).  
Example: mantainerX : contribution_descriptionX  
* Each class/function must be commented if it considered useful to understand 
the function/class purpose, otherwise (if the class/function is simple) comments
comments are redundant and must be avoided to mantain readability   
* For each class/function there must be a test   
