**Question 1** : Configure TCP/IP and “hostname” as following:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   IP ADDRESS = 172.25.X.10NETMASK = 255.255.255.0GATEWAY = 172.25.X.254DNS = 172.25.254.254Hostname = node1.example.com   `

**Answer :** 

The above parameters are the one given on the exam sheet. For the practice now, follow the video carefully to set the network parameters you will use here.

1.  You can use the nmtui command to set the IP address, the Gateway, the DNS as well as the hostname
    
2.  You may also want to use the command **hostnamectl set-hostname  node1.example.com** to set the hostname
    
3.  To check or modify the DNS configuration, you can vi in the **/etc/resolv.conf** file, search for the hostname of your server to see its DNS address
    

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`# nmtui (use this command to configure network parameters)At the end of the network configuration with nmtui, you can use the Activate a connection menu to refresh the network## DNS Issue Resolve vi /etc/resolv.conf search the name of the server` 

**Note:** After configuring the IP address of your server, you can use that to connect remotely using Visual Studio Code or any other SSH tool
