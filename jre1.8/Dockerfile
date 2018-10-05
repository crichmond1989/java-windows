# Source: https://blog.alexellis.io/continuous-integration-docker-windows-containers/

FROM microsoft/nanoserver:sac2016

RUN powershell -Command \
    $ProgressPreference = 'SilentlyContinue'; \
    Invoke-WebRequest 'http://javadl.oracle.com/webapps/download/AutoDL?BundleId=210185' -Outfile 'jreinstaller.exe'; \
    Start-Process -filepath jreinstaller.exe -passthru -wait -argumentlist "/s,INSTALLDIR=c:\\Java\\jre1.8.0_91"; \
    del jreinstaller.exe

ENV JAVA_HOME c:/Java/jre1.8.0_91

RUN setx PATH %PATH%;%JAVA_HOME%/bin

CMD "java"