# C++ Calculator
## This is a submission for the Ampify engineering placement test

### Additional code and debugging

In compiling the initial code, I received an error that _"call to 'abs' is ambiguous."_ I fixed this by adding in the ```<cmath>``` header.
  
To add division to the calculator, I first added "divide" to the enum, Type. I then added an if statement to see if a "/" was found in the user input. If so, the divide
Type would be returned. I proceeded to add a new case to the switch statement contained in the calculator class. If this was met and ```Type == divide``` the left-hand input 
would be divided by the right-hand input then returned.
  
When running the tests, I found that the test: ```cpp ResultChecker::check (Calculator ().calculate ({ 3, 5.6, Tokeniser::Type::subtract }), 2.6); ``` was failing.
I realised that 2.6 should be negative. After correcting this and re-running the tests they all passed.
  
I added the constant, pi to the calculator. I first defined it, then used an if statement to check if the string, 'pi' was contained in 
either the left-hand or right-hand side of the user input. If so the value of the constant PI, 3.141593 was returned.
  
I also added in additional tests to ensure the program could complete the required calculations:
```
10 * 4
25.3 + 18.6
3-5.6
pi * 5 (to five decimal places) 
```
While the program passed these tests, it was not displaying the output for pi * 5 to a suitable number of decimal places. Since the default number of significant figures for 
cout is 5. I therefore included the standard ```<iomanip>``` library and set the output precision to 7 significant figures so that for the calculation pi * 5, the program returned 15.70796.

### Compilation
I complied compiled within xCode using the GNU++ 17 compiler.
  
All dependencies are included within the standard library
