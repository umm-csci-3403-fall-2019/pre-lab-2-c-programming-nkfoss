# Leak report

There was a memory leak because memory was allocated to something, but not freed up after the program was done using
it.

In our case, there was function called 'strip' that allocated memory to a variable 'cleaned'

Another function called 'is_clean' called the strip function...which then passed that allocated memory to is_clean. 
This was necessary, since is_clean used that memory for a variable called 'cleaned'...which was later used to compute
something. After the computation, 'cleaned' was no longer needed and the memory could be freed.


