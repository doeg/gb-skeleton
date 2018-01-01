# Notes 


## Common Errors-
- Off by one error (especially with byte length for things like memcpy)
- Not zeroing out variables
- Not pushing/popping registers to the stack
- Missing ret (or reti)
- Forgetting to write something back out of the accumulator (e.g., incrementing a variable)
- Forgetting to rebuild the ROM
- Overlapping code sections
- Be careful accessing upper parts of HRAM because you can stomp your stack (which grows downwards from #fffe)

## RGBASM
- Errors that happen in macros are not clear in the debugger
- When reloading after setting lots of debug breakpoints, the new ROM isn't always loaded. 

## "Best" "practices"

- When writing a subroutine that will be invoked with `call`, it's a good idea to start with something like the following:

    ```asm
    ; Decide function scope
    some_function:
      push af
        push bc
          push de 
            push hl
            
            ; Function code goes here
      
            pop hl 
          pop de 
        pop bc
      pop af
      ret 
    ```

- Lowercase hex is easier to read (prefer #fffe over #FFFE). There is less contrast between letter shapes ([ref](http://uxmovement.com/content/all-caps-hard-for-users-to-read/)).
