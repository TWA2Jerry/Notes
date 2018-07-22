# Notes
A compilation of notes on C, Python, C++ and more


Before the Code
    
    Background on Unix
    - Unix supports a hierarchical file system.
    - Unix supports a pipe: where the output of one program becomes the input of another. 


The Basics

    IDEs - Compilers
    - At the moment, you are editing this "code", ie, a bunch of text, through an Integrated Development Environment(IDE).
    The IDE is essentially a program which is comprised of a source code editor (so you can edit the code which actually runs in your
    program), builder automation, and debugger.
    - The IDE may also contain what is called a COMPILER, which is a program that converts your source code to machine language. The
    compiler is required because the actual computer or machine doesn't recognise the code in C, Python etc, instead, it can only read
    what is known as machine language, ie, a whole heap of 0s and 1s.
    
    
    Projects -> Files
    - Overall, all our programs, ie, websites, games etc, start off as projects.
    - Source code: In each project, we have different files. One of these files will contain what is called the source code, and this file is called the
    source file. This file contains the majority of the code which you need to edit.
    - Header: However, there are also files which often contain the required data and functions used in a source file. These files typically include:
    
        1. stdio.h
        2. math.h
        3. stdlib.h
        
    The three of these files are already included in all C programs. /*Check this*/. The first file stands for "standard input output".
    The second files is self-explanatory (contains maths functions, variables etc.). /*The third files is currently unknown*/
    - Note that all of the above files have a .h at the end, which indicates that these files are to be included in the source file as the
    header files.
    - Also note that all projects themselves are saved under a single folder with the name of whatever you called the project. The project folder seems to be able to
    be saved anywhere. 
    
    Creating a New File
    - Once a source of constant mystery, the notion of creating a new project is now no longer shrouded in mystery: All you do, to run a new program, is click twice
    on the project in the workspace pane on the left. 
    
    Output
    - Typically, /*As far as we've seen*/ the majority of output for C is in fact displayed on the TERMINAL of the computer, rather than
    on a website or app or console. /*In fact, perhaps the terminal is the console.*/
    

Starting from Scratch
    
    IDE
    - Download an IDE from the internet. Some good editors include:
    
        1. Visual Code (Microsoft)
        2. CodeLite.
        3. CodeBlocks /*This one actually seems kinda dodgy*/
        
    That's about it! Otherwise, you don't really need anything else to create, edit and implement your own code!
    
    
The Program

    Preprocessor
    - In all programs (as we are currently aware of), we require a set of preprocessor directives which create the framework for the rest
    of the code in the source file.
    - The preprocessor directives are:
    
        1. #incldue
        2. #define
        
    The #incldue PPD(Preprocessor directive) tells the compiler to include the file at the end of the include command. For example:
    
        #include <stdio.h>
        or
        #include "Physics_constants.h"
        
    Tells the compiler to include the standard input-ouput header file. As to why for something such as the standard input output file
    can be put in the /*vectors*/ while the Physics_constants header file had to be put in quotation marks is unknown. Currently, its thought that the standard header
    files provided by the C system can use the vector quotations. 
    - The #define directive defines a certain /*variable?*/ throughout the program. For example
    
        #define SPEED_OF_LIGHT 3.00*pow(10,8)
        
    Here, we're defining the /*variable?*/ SPEED_OF_LIGHT as having a value of 3.00*(10^8). Note that since we can't actually use the
    notation 10^8 /*for reasons unknown*/ we are forced to use the index function 
        
    
    Functions
    - Functions are just lines of code which do something with an argument.
    - Functions are implemented as follows:
    
        1. Declare the function at the beginning of the file, even before the main function:
        
            type_of_function function_name(type_of_argument argument_name)
            
        2. Specify the code inside the function after the main function:
        
            type_of_function function_name(type_of_argument argument_name) {
            
                code;
            
            }
            
    - NOTE: If we don't want the function to return anything, the function type should be "void", ie,
    
        void function_name(argument) {
            code
        }
        
    
    
    
    Semicolons
    - In general, semicolons are only used after statements or declarations or commands, ie, the function printf is a command to print the control string.
    - On the other hand, conditional statements such as if-then, or while, do not require semicolons after the main block of code. 
    
    
Types

    Characters
    - The most basic data type. It's simply a single character, and the memory requirement is typically a single byte of memory.
    - It should be known that all characters have an associated integer value. Some of these are:
    
        A = 65, B = 66...
        a = 97, b = 98...

    Strings
    - Strings are essentially an array of characters, held in between quotation marks. See the section below for the definition
    of an array. An example of a string would be:
    
        "My booney lies over the ocean"
        
    - Note: The blank spaces in string still count as characters. Moreover, the end of the string also contains a final character known as
    the string terminating character, which has a value of \0, and indicates the string length has been reached.
    - Declaration: To declare a string, there are two methods:
    
        1. char * string_name = "string";
        2. char string_name[] = "string";
        
    - The first declaration above means that the string is unalterable - you can't manipulate or change the individual string elements.
    The second declaration does allow the manipulation of the string, since its now an array variable. Note that we don't actually
    need to indicate the string length in the brackets, since the compiler does this automatically//On the other hand, for multi-dimensional
    arrays, which strings ARE NOT, we would have to specify the size of different elements//
    - The First Method: It should be noted that the first method actually creates a pointer variable, string_name, which points at the memory address of the first
    string element, "s". When the compiler reads this line, it allocates a memory address for each character in the string(1 byte per character) but also allocates
    4 bytes of memory for the address of the pointer itself. As we will see, this differs slightly from the second char declaration. It should be noted that the
    first method also allows for string assignment.
    - The Second Method: The second method creates an array of charaters. When the compiler reads the line, it allocates consecutive bytes of memory to the string(again, 1
    byte per character), and the name of the array, string_name, is associated with the address of the first string character. In fact, if you try to find the address
    of the string_name array name, it will be the same as the address of the first character. This is in contrast to the first method, where the pointer variable
    would have its own, separate memory allocation.
    - However, IT MUST BE NOTED that this second method means that the array name is a constant char pointer; it cannot be decremented
    or incremented, as it points at a constant memory location. Where it points cannot be assigned essentially, whereas on the other hand, the first method created
    a pointer variable, which CAN BE reassigned. 
    - /* A third method? Is given below:
    
        char s = "string"
        
    Here, the output and error messages from the debugger seem to indicate that s is automatically read as an array.
    
    The exact error was cannot initialise a variable of type char with an lvalue of type const char [6]. 
    
        Pre-set string functions
        NOTE: To implement these functions, you have to include the #include <string.h> preprocessing directive. 
        - There are a number of in-built functions which can manipulate and use strings as arguments.
        - strlen: The first such function is strlen, which stands for string length, and 
        measures the length of the string. This can be implemented via the method below:
        
            strlen(string_name) or strlen("string")
            
        - The second is strncmp, which means string comparison, and compares the string to another string. This is used in lieu of
        the "==" operator for integers. This is implemented:
        
            strncmp(string_name, "string") or strncmp("string", string_name) or strncmp("string1", "string2")
            
        The function returns a value of 0 if the strings match, and 1 if they don't.
        - Concatenation: The third function is strncat, which means string concatenation. This involves appending, ie adding, a piece
        of one string to THE END of another. This is implemented as follows:
        
            char dest[j];
            char src[k];
            strncat(dest, src, n);
            
        - In the above line of code, the strncat function takes three arguments - the destination string, the source string and n, the maximum
        number of characters to be appended from the source to destination.
        - NOTE: the string names don't actually have to be dest or src, these are just generic placeholder names.
        
        
        Array of pointers: With regards to page 245 of C through UNIX, it works because for a normal array of characters, we would have to create an array m[][n] where
        n represents the no.sub elements in the largest element of the array m. This means that, unless all the sub arrays are of the same size, there is a significant amount of memory
        wasted as the compiler sets the uninitialised values to the \0 value. On the other hand, we can create an array of pointers, char *p[], where each element  of the array
        points to the memory address of the first character of the sub-arrays. This means a lot of space is saved, as each element (p[0], p[1] etc) will only take up
        as much space as needed for all the characters and the values of the pointers themselves. 
        
Pointers
- Pointers are simply variables which hold the value of the memory address of something, rather than the value itself.
- Pointers are declared using the following notation:

    [pointer_type] * pointer_name = &the_variable_the_pointer_points_at
    
    This assigns a local variable called pointer_name and points to the memory address of the variable, array or string. 
    
- Pointer-String: As mentioned previously, all char * variable types are just pointers to string. 
- This allows us to exploit a handy property where we're able to actually manipulate the value of a variable through a function, rather than just the argument
passed into the function. This is because if we pass a variable into the function as an argument, and then the function does something to the argument, only the
argument will be changed, rather than the variable value itself.
- On the other hand, if we pass a pointer into the function, that is, the memory address of the variable, and then change the value of the argument (the pointer)
we're also changing the value of the variable, because our program recognises the memory address of the variable and changes the value at that address.


    Array of pointers
    An array of pointers can be initialised using the following syntax:
    
        [array_type] *[array name] =
        
        
        
Structures
- Structures are pretty much just objects and classes in C. 
