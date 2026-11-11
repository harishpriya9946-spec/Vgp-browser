name: Build APK
on: [push, workflow_dispatch]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: unzip -q VGPBrowser-android-project.zip
      - uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: 17
      - uses: gradle/actions/setup-gradle@v4
        with:
          gradle-version: 8.7
      - run: gradle assembleDebug
        working-directory: VGPBrowser
      - uses: actions/upload-artifact@v4
        with:
          name: VGP-Browser-APK
          path: VGPBrowser/app/build/outputs/apk/debug/app-debug.apk
