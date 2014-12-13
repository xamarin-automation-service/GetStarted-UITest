GetStarted-UITest
=================

This is a simple first test you can run to verify your Test Cloud account works.

1) Find your API Key - this can be found on your Account Settings page on Xamarin Test Cloud. Click your name > Account Settings.
2) Replace the API_KEY value in Test.cs with your API key.
3) If you want to test locally, replace the appPath variable with the actual filepath.
4) Build the project in Debug.

To validate that your Test Cloud account works:

1) Create a New Test Run in Xamarin Test Cloud
2) Choose your devices
3) You should see a command like this (example for C# on OSX):

mono packages/Xamarin.UITest.[version]/tools/test-cloud.exe submit yourAppFile.apk APIKey --devices 83f3dba8 --series "master" --locale "en_US" --app-name "App Name" --assembly-dir pathToTestDllFolder

Normally what I do is cd into the packages/Xamarin.UITest.[version]/tools folder first in a terminal. 
Then I point at the apk/app and the test directory relative to the tools directory, which is three levels down.

The final command (broken up for clarity), run from the packages/tools directory, looks like this:

mono test-cloud.exe submit
../../../pathToApp.apk
APIKey
--devices AAAAAAA
--series "master"
--locale "en_US"
--app-name "App Name"
--assembly-dir ../../../bin/Debug

Construct this command in a terminal and run it. No modifications are required to the test project except to add your API key.

For Test Cloud purposes, the path to the app can be left blank because Test Cloud will associate the app and the tests during the upload.

Happy Testing!


