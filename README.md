Usefull-cmd
===========
Strings extraction
==================
* Extract every IP address from every files (including executables) from a folder  
`strings * | grep -oE "\b(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b"`

* Extract every `word`, and add surround of 3 lines before and 2 after, in every files (including executables) from a folder  
`strings * | grep -B 3 -A 2 'word'`

* Extract every hexadecimal key of 8 char  
`strings * | grep -oE "(?:00|01):?[a-fA-F0-9]{8}"`

* Extract every hexadecimal key of 16 char  
`strings * | grep -oE "(?:00|01):?[a-fA-F0-9]{16}"`

* Extract every hexadecimal key of 32 char  
`strings * | grep -oE "(?:00|01):?[a-fA-F0-9]{32}"`

* Extract rsa public key  
`strings * | grep -oE "AAAA[0-9A-Za-z+/]+[=]{0,3} ([^@]+@[^@]+)"`

* Extract rsa private key  
`strings * | sed -n -e '/-----BEGIN RSA PRIVATE KEY-----/,/-----END RSA PRIVATE KEY-----/ p'`

* Extract every certificate  
`strings * | sed -n -e '/-----BEGIN CERTIFICATE-----/,/-----END CERTIFICATE-----/ p'`

Convertion
==========
* Convert newlines from LF (Unix) to CR-LF (Dos):  
`$ recode ../CR-LF in.txt`
