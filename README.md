# rhino-xray

<p align="center">
<img align="center" src="./images/rhino-xray.png" alt="Rhino-Xray" />

__Rhino-xray__ is a modified version of JavaScript engine (based on Mozilla's Rhino open-source implementation of JavaScript) to help malware analyst to analyze obfuscated malicious JavaScript. Extracting the concealed strings in obfuscated JavaScripts can be very challenging and time-consuming and this tool can come in handy.

## Downloads
Rhino-xray is now available here: https://github.com/ch4meleon/rhino-xray/releases/

## Usage
* Run on JavaScript file
```
java -jar rhino-xray.jar file.js
```

* Launch debugger
```
java -cp rhino-xray.jar org.mozilla.javascript.tools.debugger.Main
```

* Run debugger on JavaScript file
```
java -cp js.jar org.mozilla.javascript.tools.debugger.Main file.js
```

## init.js
You can pre-define some JavaScript objects, functions or variables before running the malicious script.

    var WScript = new Object();
    
    WScript.CreateObject = function(name){
        print("Wscript.CreateObject: " + name);
    };
    
    function ActiveXObject() {
        this.open = function(url) {
            print("ActiveXObject.open: " + url);
        },
        this.Open = function(url) {
            print("ActiveXObject.Open: " + url);
        },  
        this.GetSpecialFolder = function(name) {
            print("ActiveXObject.GetSpecialFolder: " + name);
        },
        this.Write = function(name) {
            print("ActiveXObject.Write: " + name);
        }
        this.SaveToFile = function(name) {
            print("ActiveXObject.SaveToFile: " + name);
        },  
        this.Close = function(url) {
            print("ActiveXObject.Close: " + url);
        },
        this.run = function(url) {
            print("ActiveXObject.run: " + url);
        },
        this.deleteFile = function(url) {
            print("ActiveXObject.deleteFile: " + url);
        }   
    }

## Built-in Functions
To print out something, you may use 'alert' or 'print'
    ...
    alert("YOUR STRING");
    ...

or

    ...
    print("YOUR STRING");
    ...

## Contact
ch4meleon@protonmail.com
> MichaelL
