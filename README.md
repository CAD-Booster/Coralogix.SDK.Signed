# Coralogix.SDK.Signed
If you're stuck needing strong-named assemblies, but you still want to use Coralogix, then this package should help you. We have downloaded the official package, signed and published it.

Inspired by the signed version of [Flurl](https://github.com/ellenfieldn/Flurl.Signed)

## NuGet Packages ##
Official, unsiged version: [Coralogix.SDK](https://www.nuget.org/packages/Coralogix.SDK)<br/>
This package: [Coralogix.SDK.Signed](https://www.nuget.org/packages/Coralogix.SDK.Signed/1.1.9)

## Caveats
* We do not own the copyright of this code and we are not affiliated with Coralogix in any way. We asked them for a signed version but it wasn't a priority for them, so we created our own for the time being.
* These are not built from source, we simply get the existing assemblies from NuGet, sign them and publish them back to NuGet.

## How to create your own ##
1. Clone the repository
1. Open the Developer Powershell in Visual Studio or a Command Prompt
1. Go into the Nuget Package folder
1. Create a package by calling: nuget pack Coralogix.SDK.Signed.nuspec

### To publish it to a local NuGet libray ###
To add the package:
1. nuget add "path to .nupkg file" -source "path to local NuGet feed"

To remove the package:
1. nuget delete Coralogix.SDK.Signed x.x.x -source "path to local NuGet feed"

### If you want to publish it on NuGet ###
1. Purchase a code signing certificate 
1. Register the certificate on nuget.org under your account 
1. nuget sign "path to .nupkg file" -CertificateFingerPrint "your certificate fingerprint" -Timestamper "url to timetamper"
1. Upload the .nupkg file on nuget.org 
