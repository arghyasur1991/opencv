## OpenCV: Open Source Computer Vision Library

### Resources

* Homepage: <http://opencv.org>
* Docs: <http://docs.opencv.org/master/>
* Q&A forum: <http://answers.opencv.org>
* Issue tracking: <https://github.com/opencv/opencv/issues>

### Contributing

Please read the [contribution guidelines](https://github.com/opencv/opencv/wiki/How_to_contribute) before starting work on a pull request.

#### Summary of the guidelines:

* One pull request per issue;
* Choose the right base branch;
* Include tests and documentation;
* Clean up "oops" commits before submitting;
* Follow the [coding style guide](https://github.com/opencv/opencv/wiki/Coding_Style_Guide).


For building OpenCV for android using libc++ instead of gnustl_static, clang instead of gcc and with c++11 support, use cmake with following cmd line options
`cmake -GNinja -DCMAKE_BUILD_TYPE=Release -DWITH_OPENCL=OFF -DCMAKE_TOOLCHAIN_FILE={ANDROID_NDK_HOME}/build/cmake/android.toolchain.cmake -DENABLE_CXX11=ON -DANDROID_TOOLCHAIN=clang "-DANDROID_STL=c++_static" -DANDROID_ABI=arm64-v8a -DANDROID_SDK_TARGET=23 -DANDROID_NATIVE_API_LEVEL=23 -DANDROID_ARM_NEON=ON -DANDROID_SDK={ANDROID_SDK_HOME} -DANDROID_NDK={ANDROID_NDK_HOME} -DBUILD_ANDROID_PROJECTS=OFF ..`

Before that download android sdk tools version 25.2.3 and build tools version 26.0.2 otherwise opencv build will be corrupt. Remove or rename the folders for later versions in ${ANDROID_SDK}/build-tools/ folder and remove or rename the ${ANDROID_SDK}/tools folder
