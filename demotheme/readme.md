#Main directory for theme files
Apart from the very useful defaults.php file, pretty much everything should be in the subdirectories of this directory.

defaults.php provides the ability to replace 'ownCloud' and the strapline with your own branding without having to hard code it to your templates.

Please be carefuly with the defaults.php file - it is very sensitive to extra spaces and particularly sensitive if you edit it on a *nix server using a Windows client. Make sure it stays in a *nix format - DOS formatted text files often cause the Windows ownCloud Client to stop working with a XML declaration error. This error found in ownCloud server versions 7.0.4 and 8.0.0 with Windows client 1.7.1 (build4382)
