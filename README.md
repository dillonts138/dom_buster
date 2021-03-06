# dom_buster
-Program written by Dillon Shaver and John Marinelli:

-dom_buster is an input fuzzer that utilizes selenium and it's browser drivers to test a 
series of xss crossite script injection attacks on input fields
on a webpage.

-requires selenium to use:
https://www.selenium.dev/documentation/webdriver/getting_started/

-This program is written in python and thus requires the python vesion

-Written for the google chromw browser, will not function for other browsers


Usage
-----------------------------------------


   This program is an input fuzzer for input boxes on websites. 
   It tests all the inputs on the webpage for crossite scripting vulnerabilities.
   It does so by cycling through a list of payloads and inputting them into all  
   the active and displayed input fields on the webpage and checking for an alert box.  
   
   All default input payloads can be found in the culled_xss_list.txt file inside the res folder.
   Custom payloads can be used by utilizing the custom xss list flag as described below and passing the path to the file.
   
   *WARNING*: All custom xss files should have each xss input on its own line, otherwise undefined behavior can occur.
   
   *WARNING*: Should NOT be tested on websites you do not own or not set up for such purposes for obvious ethical reasons! 
   
   Please use responsibly.
   
   Syntax and use
    
    To get help info:
    python3 dom_buster.py -h
        or
    python3 dom_buster.py --help
    
    
    Run dom_buster on url (no xpath): 
    python3 dom_buster --u=Your_Url_Path
        or
    python3 dom_buster --url=Your_Url_Path
        or
    python3 dom_buster --URL=Your_Url_Path
    
    
    Run dom_buster on url with xpath:
    python3 dom_buster --u=Your_Url_Path --x=Your_Xpath
        or
    python3 dom_buster --url=Your_Url_Path --xpath=Your_Xpath
        or
    python3 dom_buster --URL=Your_Url_Path --XPATH=Your_Xpath
    
    
    Use Custom xss list (xpath flag also allowed with these calls):
    python3 dom_buster --u=Your_Url_Path --l=res/path_to_xss_textfile
        or
    python3 dom_buster --url=Your_Url_Path --list=res/path_to_xss_textfile
        or
    python3 dom_buster --URL=Your_Url_Path --LIST=res/path_to_xss_textfile
   
   Parameters and Options: 

   -h : help -description of program use, parameters, and options.
   
   --url=, --u= : url parameter -Url path to the website to run the payload injection on.
   
   --xpath=,--x= : [Optional] xpath parameter -Path to the element if input fields is embedded behind buttons or routing. Can be found by copying the xpath from the webpages source code in the browser's inspect tool.
   
   --l, --list, --LIST : [Optional] custom xss list parameter: -Path to the text file that holds the custom xss calls you'd like to try on the input boxes

