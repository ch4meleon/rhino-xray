rhino-xray
==========

<p align="center">
<img align="center" src="./images/rhino-xray.png" alt="Rhino-Xray" />

__Rhino-xray__ is a modified version of JavaScript engine (based on Mozilla's Rhino open-source implementation of JavaScript) to help malware analyst to analyze obfuscated malicious JavaScript. Extracting the concealed strings in obfuscated JavaScripts can be challenging and time-consuming and this tool can come in handy for that.

Usage
----
* Run againsts a JavaScript file
```
java -jar rhino-xray.jar file.js
```

* Launch debugger
```
java -cp rhino-xray.jar org.mozilla.javascript.tools.debugger.Main
```

* Run debugger againsts a JavaScript file
```
java -cp js.jar org.mozilla.javascript.tools.debugger.Main file.js
```

# Contact
ch4meleon@protonmail.com
> MichaelL
