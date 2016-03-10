# GooglePlayGameServicesDemo

## Intro

This project illustrates how to incorporate Google Play Game Services with a Unity project that will be built for iOS on Unity Cloud Build. Since cocoapods functionality is not currently supported in Cloud Build, it is necessary to use the manual installation instructions at the following link:

[Getting Started with Play Games Services for iOS: Manual SDK Install](https://developers.google.com/games/services/ios/quickstart#option_2_manual_installation)

In order to modify the generated XCode project during a build in Unity Cloud Build, it is necessary to use the Unity [XCode Manipulation API](https://bitbucket.org/Unity-Technologies/xcodeapi). This API allows the addition of the required bundles and frameworks for Play Game Services to operate. The code repsonsible for this configuration is in Assets/Editor/PostProcessor.cs, where directives are used to determine if the build is local or in Cloud Build and acts accordingly. The PBXProject class is loaded from an XCode `.pbxproj` file and represents the XCode project.

## SDK Information

This example project includes the current versions of the SDK files mentioned in the install instructions link above. When using the post-export functionality in your own project, you should download the latest available version of the SDK dependencies available as the included resources may be out of date. As of the creation of this project, the following dependencies are located in Assets/ThirdParty/Google/sources:

- Google Sign-In SDK 2.4.0
- Play Games C++ SDK 2.1
- Google+ iOS SDK 1.7.1

## Helpful Links

[PBXProject class reference](http://docs.unity3d.com/ScriptReference/iOS.Xcode.PBXProject.html)