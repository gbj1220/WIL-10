# What I learned in week 10

## Node:

### *readline*:
* this module provides an interface for reading data from a file one line at a time
* must be used on the front end to read all of your data

### *writeFile:*
* the fs.writeFile() method is used to asynchronously write data to a file
* updates your JSON file every time you make a change to your back end data

## **Syntax** 
fs.writeFile(file, data, options, callback)

**file:**
* a string, buffer, or URL / file description integer that denotes the path of where the file was written

**data:**
* a string, buffer, typedArray or dataView that will be written to the file

**options:**
* a string or object that can be used to specify option parameters that will affect the output
* default encoding is 'utf8'

**callback:**
* the function that would be called when the method is executed

## **Example**
const fs = require('fs'); 
  
let data = "This is a file containing a collection of books."; 
  
```
fs.writeFile("books.txt", data, (err) => { 
  if (err) 
    console.log(err); 
  else { 
    console.log("File written successfully\n"); 
    console.log("The written has the following contents:"); 
    console.log(fs.readFileSync("books.txt", "utf8")); 
  } 
});

``` 
### **readFile:**

* a method built in to node used to read a file such as a JSON

* essentially just reads your JSON file and pushes it into whatever you call it on

* must require 'fs' in order to use it

## **Syntax:**
fs.readFile (filename, encoding, callback function)

* with readFile, for now at least, we do not need encoding

**fileName:**
* the name of the file to read or the entire path if stored in different location

**encoding:**
* holds the encoding file

**callback function:**
* called after reading file, takes in two parameters (VERY IMPORTANT!) the first param is always err and the second is data

* err is always called first to check and see if you have any errors

## **Example:**
var fs = require('fs'); 
  
fs.readFile('text', function(err, data) { 
 if (err) {
   throw err;
 } 
  console.log(data); 

}); 
