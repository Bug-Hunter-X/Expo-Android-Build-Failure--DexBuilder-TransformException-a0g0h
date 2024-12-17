# Expo Android Build Failure: DexBuilder TransformException

This repository demonstrates a common issue encountered when building Android APKs using the Expo CLI. The build process fails during the DEX transformation stage, resulting in a `TransformException`. This problem is often associated with projects containing a large number of dependencies or complex code.

## Bug Description

The primary symptom is a build failure during the Android build process, indicated by an error message related to `com.android.build.api.transform.TransformException` and the DexBuilder. The exact error message can vary, but it typically involves a long classpath and points to problems during class transformation into Dalvik Executable (DEX) format.

## Reproduction Steps

1. Clone this repository.
2. Install the dependencies: `npm install` or `yarn install`.
3. Attempt to build the Android APK using the Expo CLI: `expo build:android`.

## Solution

The solution involves a multi-pronged approach to reduce the size of the app and optimize its dependencies.  The provided `bugSolution.js` contains several techniques that help to solve this issue including code-splitting and tree-shaking with rollup.  Detailed information on these techniques can be found in the comments of `bugSolution.js`.

## Additional Tips

* Regularly clean your project: `expo prebuild --clean`
* Consider ProGuard to shrink your code and optimize resources. Refer to Expo's documentation on code optimization and ProGuard for more detail. 
* Upgrade dependencies to the latest version to take advantage of potential performance improvements.  
