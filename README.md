# Installing Docker on Windows Server 2016

First, install the Docker-Microsoft PacheManagement Provider from the PowerShell Gallery
```
PS> Install-Module -Name DockerMsftProvider -Repository PSGallery -Force
```
Next, you use the PackageManagement PowerShell module to install the latest version of Docker
```
PS> Install-Package -Name Docker -ProviderName DockerMsftProvider
```
When PowerShell asks you whether to trust the package source `DockerDefault`, type `A` to continue the installation.
When the installation is complete, reboot the computer.
```
PS> Restart-Computer -Force
```

## Install Docker-Compose

Make sure to include to correct docker-compose version

```
PS> Invoke-WebRequest https://github.com/docker/compose/releases/download/1.12.0/docker-compose-Windows-x86_64.exe -UseBasicParsing -OutFile $env:ProgramFiles\docker\docker-compose.exe
```
