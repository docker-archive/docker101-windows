# escape=`
FROM microsoft/iis:windowsservercore

HEALTHCHECK --interval=5s `
 CMD powershell -command `
    try { `
     $response = Invoke-WebRequest http://localhost -UseBasicParsing; `
     if ($response.StatusCode -eq 200) { return 0} `
     else {return 1}; `
    } catch { return 1 }

COPY index.html C:\inetpub\wwwroot