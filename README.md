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
java -cp rhino-xray.jar org.mozilla.javascript.tools.debugger.Main file.js
```

## init.js
Sometimes malicious JavaScripts have calling to functions that will break your analysis in runtime. You can pre-define JavaScript objects, functions or variables before executing it.

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
To print out something, you can use 'alert' or 'print':

    alert("my string");
    print("another string...");

## Screenshots
<img align="center" src="./images/1.png" alt="Screenshot #1y" />

## Contact
ch4meleon@protonmail.com

