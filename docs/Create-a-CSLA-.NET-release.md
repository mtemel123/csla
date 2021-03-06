Prerequisites
-------------
You must have:

1. PC
 1. Windows 10
 1. Visual Studio 2017 with the latest updates
  1. Xamarin
  1. UWP SDK

NuGet release
-------------
1. Pull the latest code from MarimerLLC/csla
1. Open the csla.build.sln
   1. Update version numbers
      1. `cd /Source`
      1. `grep -rl --include=*.cs --include=*.csproj '4.7.200' | tee | xargs sed -i 's/4.7.200/4.8.100/g'`
   1. Build the solution in Release mode; Any CPU
1. Do NuGet release
   1. Open a powershell window
   1. Run the `nuget\Build All.ps1` script (add /prerelease:yymmddxx for test release)
   1. Make sure you have Rocky's NuGet key installed (see Nuget.org)
   1. Run the `nuget\Push All.ps1` script

Finalize Release
----------------
1. Update GitHub
   1. Update [releasenotes.md](https://github.com/MarimerLLC/csla/blob/master/releasenotes.md)
   1. Commit all changes to git
   1. Create PR 
   1. Accept PR
1. In the GitHub releases web page create the release
   1. Create a new release at HEAD using the version number (such as v4.6.400)
   1. Mark the release as pre-release or release
