Demo showcasing the differences between Bazel and xcodebuild when generating `.ipa` with signed xcframeworks.

Tested with Xcode 15.2

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

- Open `xcode/PrivacyDemo/PrivacyDemo.xcodeproj`;
- Configure the code sign settings (to be able to generate the archive);
- Product -> Archive
