# Memory 

## Overview
In some lower-level languages, it is very easy to create code that is prone to memory corruption or manipulation. Although many applications are not vulnerable because of their choice of languages, even within these managed languages, such as Java EE and .Net, it is possible to call unmanaged code either directly or via third-party libraries. It is the responsibility of the designers and developers of an application to consider memory management in each of these libraries to ensure that data is not leaked or the application is not taken offline by an attacker taking advantage of these memory vulnerabilities.

## Background
Not only is all the data of an application stored in memory at some point, but the very execution of a program is governed by values stored in memory. Temporary variables and the location of the function to return to are stored in a stack per-thread and other data that is created, especially using a keyword like "new" or "alloc" is kept in the program's heap. It is therefore possible to either access data present in memory by tricking the application into revealing it, to alter the behaviour generally of the application, either for advantage or to deny service and also possible for an attacker to run attack code by modifying the memory contents of a location that the program is going to use for its next function execution.

In general, these vulnerabilities exist partly due to older operating systems not segregating memory effectively and more commonly now by low-level language primitives which provide little or no protection for the way in which memory can be assigned or the size of data that can be copied into a memory location. These decisions were likely made for performance reasons but can still exist in code that might still be called from modern web applications - legacy or otherwise.

There are many ways in which a vulnerable application can be attacked but these tend to fall into two distinct modes. The first is to try and infiltrate the server and somehow upload a block of attack code. This could be done, for instance, by using an unchecked "upload" function on an application, but often this would not be enough by itself. The second mode is to send wildly incorrect data to form inputs in order to both find out whether the application is validating correctly and secondly to attempt to cause the memory corruption to occur. This is naturally easiest when the attacker has the source code and can work out roughly what they want to do although an attacker who is perhaps not trying to achieve anything specifically might equally be happy causing your site to fail.


## Principles (if any)
Some principles are in common with secure development including not trusting input that arrives from across a trust boundary (another process, client, machine etc.) and not making assumptions about the behaviour of third-party libraries that you might be calling or might be calling into your code.

Other principles require more specific knowledge and experience, especially when it comes to reviewing code in order to decide whether it is secure, or otherwise taking decisions where security is balanced with performance, particularly on embedded devices that have reasonable constraints on the memory and CPU cycles that can be used.

As with many OWASP controls, defence-in-depth and careful use of unit tests can help provide confidence in the level of risk your application is taking. Another principle that you should be comfortable with is logging system behaviour so that detection of potential attacks can be made sooner and actions taken if possible. This might not be possible on an application that is deployed to e.g. multiple embedded devices but is more reasonable on a single application.

## Positive controls 

### Choosing a secure language
The most secure control against memory attack is to use a language that does not allow you to directly manipulate memory or contains exception handling where you might attempt to do something harmful. For instance, Java, .Net and PHP are all secure against memory tampering as long as you do not use them to call extensions written in C/C++ or equivalent low-level languages. That is not to say that an application automatically becomes completely immune to memory related attacks. For instance, an unchecked upload capability can expose to the server to an out-of-memory attack which might take the server down or at best cause it to become largely unresponsive.

### Using library classes
In many cases, where you have to use a low-level language, you do not have to use the lowest level construct in order to achieve what you need. For instance, in C++, you could use a char[] for strings but you can also choose to use the Standard Template Library (STL) string class or another library class to achieve a much more secure protection against mis-use for a small increase in overhead.

### Active intrusion detection
If your application is potentially vulnerable to memory attacks i.e. it uses unmanaged code at some level, then a useful control is to detect malformed data at as high a level as possible and rather than simply stopping, you can take measures to block the offending IP address for a short period to make it hard for an attacker to probe weaknesses in your system. For instance, if you have a function that takes an email address and you validate it and realise that it is excessively long even though you know that your client always validates the data, then you can assume an attack is occurring rather than a simple user error and you can take more direct action.

### Input validation
Another major security control is simple input validation. Please see the other chapter for more details but it is best to whitelist validate all user input, including maximum lengths and this must be done on the server. It can optionally be done on the client but client validation can be bypassed and is therefore not sufficient by itself. Validation won't guarantee that your application is immune since a coding error could present a problem even with data that is otherwise validated. An example mistake is an input allowing 255 characters and a buffer being set to 255 bytes in size despite requiring an additional byte for the NULL terminator character. Sending 255 characters to the buffer could pass validation and still cause a problem with the underlying code.


## Unit or Integration Test Cases

## Abuse Cases

## Negative patterns

### Control that should never ever appear under pain of infinite nyan cat

e.g. shared knowledge questions or answers, or dynamic SQL queries

## References

***

## Secure string handling
One of the most common causes of buffer overflows are caused when strings are copied using pointers to character buffers (e.g. char*). This is because the size of the string is determined by a null terminator (a zero character) placed after the last character in the string. When copying between strings, if this terminator is not handled correctly, the string becomes implicitly longer, its length determined by the (random) location of the next null terminator in memory. The following examples demonstrate some classic mistakes in string handling in C/C++.

    #define MAX_STRING_LENGTH 255
    public void MyFunction(char* input)
    {
        char buffer[MAX_STRING_LENGTH];
		    strcpy(buffer, input);				// Potential buffer overflow since the input string can be longer than the destination buffer
    }
	
	public void MyFunction(char* input)
	{
		// A simple check to avoid this problem
		if ( strlen(input) > MAX_STRING_LENGTH )
			return;		// Or handle error etc.
	
		char buffer[MAX_STRING_LENGTH];
		strcpy(buffer, input);				// Potential buffer overflow since the destination buffer is only large enough for a string of 254 length + null terminator
	}
	
	public void MyFunction(char* input)
	{
		// A simple check to avoid this problem
		if ( strlen(input) > MAX_STRING_LENGTH )
			return;		// Or handle error etc.
	
		// Recommend using + 1 to make it obvious that you have allowed for the null terminator
		char buffer[MAX_STRING_LENGTH + 1];
		strcpy(buffer, input);
	}
	
Similar issues exist for when copying general memory buffers, which would not have a null terminator and therefore no explicit marker for the end of the data. In these scenarios, you should always provide a length parameter so you know how long the input data is but you should still ensure this value is in a sensible range to avoid someone trying to corrupt the stack by copying more data than has actually been provided. These cases are much rarer in web application development but could occur when, for instance, the user uploads an image or other binary file.

    public void MyFunction(void* input, size_t length)
	  {
	     char* buffer = (char*)malloc(length);
		   memcpy(buffer, input, length); 	// Will work but why not include a sanity check on the value of length?
	 }


## Enabling secure memory flags
## Memory management
## Stack overflows
## Heap overflows
## Integer overflows
Integer overflows occur due to the nature of how integer values are stored in memory. What happens when, for example, you add 1 to an integer that is already set to 11111111? Answer - it wraps round to 00000000 usually, in other words 'some number' + 1 = 0. This can be worse for signed types since the most significant bit is used to store whether a value is positive or negative. So adding 1 to a SIGNED integer that contains 01111111 doesn't increase the value by 1 by takes the value from its largest maximum value to one of its smallest possible values. Another issue can occur when adding two large unsigned integers, which might cause the value to wrap into something small instead. Any cases in your code where this is possible can therefore have unintended consequences.

    // The following would work in many situations but if age was large enough, the buffersize could end up being
    // really small due to integer overflow. Buffer overflow would then be likely
    public void MyFunction(int age)
    {
        int buffersize = age + age;
        char* buffer = (char*)malloc(buffersize);
        // etc..
    }
    
    // If this was designed to have age1 > age2, the values might be assumed to be correct. If they are the wrong way round, however
    // and the buffersize ends up being negative, this would be interpreted as a very large unsigned number when mallocing the buffer
    public void MyFunction(byte age1, byte age2)
    {
        int buffersize = age1 - age2;
        char* buffer = (char*)malloc(buffersize);       // Potential cause of out-of-memory error
        // etc..
    }
    
The issues here can easily be avoided by simple range checks and/or error handling to simply justify assumptions made about the values given. Also, it is preferable (although sometimes slightly awkward) to use unsigned types where appropriate. This can sometimes be hard because library functions can often take a signed type even when it doesn't need to be and casting is required to force these to work correctly. A more extensive version of the second function above, coded very defensively, might look like this:

    public void MyFunction(unsigned char age1, unsigned char age2)
    {
        if ( age2 >= age1 )
        {
            error("Age 1 must be greater than age 2");
            return;
        }
        if ( age1 > 120 || age2 > 120 )
        {
            error("The age given must be less than 120");
            return;
        }
        int buffersize = age1 - age2;
        char* buffer = (char*)malloc(buffersize);
        // etc..
    }

A few languages have built-in assertion syntax to explicitly state your assumptions about input values. These can be left on at runtime to stop execution before anything unexpected happens.

