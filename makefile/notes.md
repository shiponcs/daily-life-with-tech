
1. Target: 
	- (writing target and other basics aren't convered)
   	- first target is always called if no target is mentioned when calling make
 
 3. Variable:
  	- Declare a variable: `a := file1 file2`
  	- Reference a variable: `${a} or $(a)`
  
 4. Wildcard *:
  	- `*` searches file system for matching. eg:
    ```
      # Print out file information about every .c file
      print: $(wildcard *.c)
	    ls -la  $?
    ```
    
5. Some notations: 
  	- $^: all prerequisites
  	- $?: the names of all prerequisites newer than the target
  	- $@: name of target
  	- $<: firt prerequisite
7. 
