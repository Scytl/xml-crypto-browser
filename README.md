## xml-crypto-browser
An xml digital signature library for javascript. Forked and adapted from https://github.com/yaronn/xml-crypto

## Install
is a little rough by now, just copying files from "lib" folder.:

## pre requisita
* xpath: https://github.com/yaronn/xpath.js (not properly versioned, commit: 032e4c7191802bb3c81273354f3dc3db120cb47b


## Verifying Xml documents

`````javascript
	var signature; //signature in string format
	var xml; //xml in string format
	var publicKey;
	var sig = new SignedXml();
	sig.keyInfoProvider = new KeyInfo(publicKey);
        sig.loadSignature(signature);
        var res = sig.checkSignature(xml);
`````

Note: 

The xml-crypto api requires you to supply it separately the xml signature ("&lt;Signature&gt;...&lt;/Signature&gt;", in loadSignature) and the signed xml (in checkSignature). The signed xml may or may not contain the signature in it, but you are still required to supply the signature separately.

## Supported Algorithms
The first release always uses the following algorithems:

* Exclusive Canonicalization http://www.w3.org/2001/10/xml-exc-c14n#
* SHA1 digests http://www.w3.org/2000/09/xmldsig#sha1
* RSA-SHA1 signature algorithm http://www.w3.org/2000/09/xmldsig#rsa-sha1

you are able to extend xml-crypto with further algorithms.
