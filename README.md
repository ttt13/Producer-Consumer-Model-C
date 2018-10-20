# Producer-Consumer-Model-C
Models the producer-consumer problem of multi-process synchronization. 
One group of threads model candy factories which generate one candy at a time, inserting them into the bounded buffer.
The other group of threads model kids who eat candy one at a time from the buffer.
We wish to manage the access to this bounded buffer.
The program will accept 3 arguments: ./candykids <#factories> <#kids> <#seconds>
  1. The number of factories to spawn
  2. The number of kids to spawn
  3. Number of seconds to allow the factories to run for.

# Producer/Consumer Operation
There are ten main steps to this application:
  1. Extract arguments.
  2. Initialize Modules
  3. Launch factory threads
  4. Launch kid threads
  5. Wait for requested time
  6. Stop factory threads
  7. Wait until no more candy
  8. Stop kid threads
  9. Print statistics
  10. Cleanup any allocated memory

# Candykids.c
Main application holding factory thread, kid thread, and main() function. Plus some other helper functions, and some #defined constants.

# Bbuff.c
Bounded buffer module. Uses semaphores for blocking.

# Stats.c
Statistics module.
  1. Count the number of candies each factory creates. Called from the candy-factory thread
  2. Count the number of candies that were consumed from each factory.
  3. For each factory, the min, max, and average delays for how long it took from the moment the candy was produced (dynamically allocated)      until consumed (eaten by the kid). 
  

# Makefile
Compiles all the .c files and link together the .o files.
