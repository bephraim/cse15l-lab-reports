# Lab Report 2

##Part 1: StringServer

Below is a screenshot of the code for StringServer:
![Image](lab2image1)

The following image shows a use of /add-message. After input, the url reads: 
> http://localhost:4141/add-message?s=Hello

![Image](lab2image2)

The input above uses the method: getPath() on the URI paramter *url*, which retries the path(which is the input) of URL into a string. It then uses the .equals() method of the String class, with the argument "/add-message" to determine if the given path is what we're looking for. getQuery() is also used to get the string that is added to the output on the page by finding the string that is after the equal sign (which is done by using split("=")). The string that is found from this process is added to "s", which is the varaible name for the string that represents the entirety of the output and updates with a new line everytime the "/add-message" command is run. Finally, String.format() properly formats the input in the uri to a string that is properly displayed on the page with the parameters "$s", which properly formats a string, and "s".

The follow image shows an invalid command in the URI line:
![Image](lab2image3)

The input from the screenshot uses getPath() to retrieve the path of the URI into a string. It then uses .equals() (with the paramter "/add-message" to determine of the write command is used. An inconsistency is found, resulting in the code returning the error message: "*404 Error Not Found!*". The string that holds all of the inputs does not get updated when this happens.

##Part 2: Debugging



