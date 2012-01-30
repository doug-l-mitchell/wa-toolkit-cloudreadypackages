Windows Azure Toolkit for iOS (Cloud Ready Packages)
===

The Windows Azure Toolkit for iOS is a toolkit for developers to make it easy to access Windows Azure storage services from native iOS applications.  The toolkit can be used for both iPhone and iPad applications, developed using Objective-C and Xcode.  

The toolkit works in two ways – the toolkit can be used to access Windows Azure storage directly, or alternatively, can go through a proxy server.  The proxy server code is the same code as used in the WP7 toolkit for Windows Azure (found [here](http://watwp.codeplex.com/)) and negates the need for the developer to store the Azure storage credentials locally on the device.  If you are planning to test using the proxy server, you’ll need to download and deploy the services found in the [cloudreadypackages](https://github.com/microsoft-dpe/cloudreadypackages) here on GitHub.   

Each package contains a getting started on how to configure and upload your package to Windows Azure.

The Windows Azure Toolkit for iOS is made available as an open source product under the Apache License, Version 2.0.  

## Generating the Certificate on your Mac

You will need to create a certificate to support SSL or get one from a trusted authority. If you are going to create one yourself, you can by doing the following:

* open a terminal window
* enter the command: **openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout iOSWAToolkit.pem -out iOSWAToolkit.pem**
	* iOSWAToolkit is the name of the file you want and can be anything you like.
	* This will create a certificate that you can use to create the PKCS12 certificate. This command will ask for all the information for your cert that you enter.
* enter the command: **openssl pkcs12 -export -out iOSWAToolkit.pfx -in iOSWAToolkit.pem -name "iOSWAToolkit"**
	* iOSWAToolkit is the name of the file you want and can be anything you like.
	* This will ask you for a password that you need to remember so you can enter it when uploading to Windows Azure.
* enter the command: **openssl x509 -outform der -in iOSWAToolkit.pem -out iOSWAToolkit.cer**
	* This will export a certificate with the public key which is what you will need for the service config file.

## Contact

For additional questions or feedback, please contact the [team](mailto:wwegner@microsoft.com).