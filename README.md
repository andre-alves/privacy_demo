# privacy_demo

Demo showcasing the differences between Bazel and xcodebuild when generating `.ipa` with signed xcframeworks.

## Bazel

```
bazel build //app:app --config app_store
```

or

```
bazel build //app:app.xcarchive --config app_store
```

Check `bazel-out/` outputs.

## Xcode

TBD.
