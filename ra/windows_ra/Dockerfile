FROM microsoft/dotnet-framework:4.7


#================================
# Download java
#================================
RUN powershell (new-object System.Net.WebClient).Downloadfile('http://javadl.oracle.com/webapps/download/AutoDL?BundleId=210185', 'C:\jre-8u91-windows-x64.exe')
RUN powershell start-process -filepath C:\jre-8u91-windows-x64.exe -passthru -wait -argumentlist "/s,INSTALLDIR=c:\Java\jre1.8.0_91,/L,install64.log"
RUN del C:\jre-8u91-windows-x64.exe

#================================
# Download Microsoft dependencies
#================================
RUN powershell (new-object System.Net.WebClient).Downloadfile('https://dist.nuget.org/win-x86-commandline/latest/nuget.exe', 'C:\nuget.exe')
RUN powershell (new-object System.Net.WebClient).Downloadfile('https://www.microsoft.com/en-us/download/confirmation.aspx?id=48159', 'C:\BuildTools_Full.exe')


CMD [ "c:\\Java\\jre1.8.0_91\\bin\\java.exe", "-version"]
