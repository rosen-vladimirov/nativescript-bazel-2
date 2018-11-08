# NativeScript with Bazel

This project demonstrates how to build NativeScript project with Bazel. Please follow the steps below:
1. Ensure your ANDROID_HOME variable is set correctly.
2. Clone this repo
3. Execute `tns prepare android` in the cloned repo dir - this will prepare the project and add all required Bazel files
4. Execute `bazel build //platforms/android:android`

# Issues

The command fails on Ubuntu 18 with error:
```
ERROR: /home/rvladimirov/nativescript-bazel-2/platforms/android/BUILD.bazel:92:1: Building platforms/android/libcompiled_static_bindings.jar (9 source files, 1 source jar) failed (Exit 1): java failed: error executing command 
  (cd /home/rvladimirov/.cache/bazel/_bazel_rvladimirov/159b567e2329b0ec75c706e5a1ec0e37/execroot/__main__ && \
  exec env - \
    LC_CTYPE=en_US.UTF-8 \
  external/embedded_jdk/bin/java -XX:+UseParallelOldGC -XX:-CompactStrings '--add-exports=jdk.compiler/com.sun.tools.javac.api=ALL-UNNAMED' '--add-exports=jdk.compiler/com.sun.tools.javac.code=ALL-UNNAMED' '--add-exports=jdk.compiler/com.sun.tools.javac.comp=ALL-UNNAMED' '--add-exports=jdk.compiler/com.sun.tools.javac.file=ALL-UNNAMED' '--add-exports=jdk.compiler/com.sun.tools.javac.main=ALL-UNNAMED' '--add-exports=jdk.compiler/com.sun.tools.javac.tree=ALL-UNNAMED' '--add-exports=jdk.compiler/com.sun.tools.javac.util=ALL-UNNAMED' '--add-opens=jdk.compiler/com.sun.tools.javac.file=ALL-UNNAMED' '--patch-module=java.compiler=external/bazel_tools/third_party/java/jdk/langtools/java_compiler.jar' '--patch-module=jdk.compiler=external/bazel_tools/third_party/java/jdk/langtools/jdk_compiler.jar' '--add-opens=java.base/java.nio=ALL-UNNAMED' '--add-opens=java.base/java.lang=ALL-UNNAMED' -jar external/bazel_tools/tools/jdk/JavaBuilder_deploy.jar @bazel-out/android-armeabi-v7a-fastbuild/bin/platforms/android/libcompiled_static_bindings.jar-0.params)
/com/tns/NativeScriptActivity.java:27: error: [MissingSuperCall] This method overrides android.support.v4.app.SupportActivity#onSaveInstanceState, which is annotated with @CallSuper, but does not call the super method
	protected void onSaveInstanceState(android.os.Bundle param_0)  {
	               ^
    (see https://errorprone.info/bugpattern/MissingSuperCall)
Target //platforms/android:android failed to build
INFO: Elapsed time: 1.871s, Critical Path: 0.87s
INFO: 0 processes.
FAILED: Build did NOT complete successfully
```

Same project can be build successfully with:
-  `tns build android`
- Opening the `<cloned repo dir>/platforms/android` in Android Studio and building it from there.
