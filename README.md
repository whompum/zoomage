# zoomage
A simple pinch-to-zoom ImageView library for Android with an emphasis
on a smooth and natural feel. Great for personal image gallery experiences.

[![Build Status](https://travis-ci.org/jsibbold/zoomage.svg?branch=master)](https://travis-ci.org/jsibbold/zoomage)

## Gradle
```groovy
repositories {
    jcenter()
}

dependencies {
    compile 'com.jsibbold:zoomage:1.0.0'
}
```

# Using It

## XML Attributes

```xml
restrictBounds="true|false"
```
Restricts the bounds of the image so it does not wander outside the border of the ImageView when it's smaller than the frame size,
and restricts the bounds to stop at the edges of the ImageView when the image is larger than the frame size. Default value is false.

```xml
animateOnReset="true|false"
```
Image will animate back to its starting size whenever it is reset if true, and will snap back to its starting size when false.
Default value is true.

```xml
autoReset="UNDER|OVER|ALWAYS|NEVER"
```
Determines at what times the image will reset to its starting size. Note that UNDER, OVER, and ALWAYS all have the effect of
resetting the image to its starting position even if its size has not changed. Default value is UNDER.

```xml
autoCenter="true|false"
```
This will cause the image to pull itself into view on-screen if it is partially off-screen. Default value is true.

```xml
minScale="{float greater than 0}"
```
The minimum allowed scale for the image. Ideally this should be less than 1, must be greater than 0, and must
be less than maxScale. Default value is 0.6.

```xml
maxScale="{float greater than 0}"
```
The maximum allowed scale for the image. Ideally this should be greater than 1, must be greater than 0, and must
be greater than minScale. Default value is 8.

```xml
zoomable="true|false"
```
Sets whether zooming is allowed. Default value is true.

```xml
translatable="true|false"
```
Sets whether translation is allowed. Default value is true.


## Example Usage
```xml
    <RelativeLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:zoomage="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="match_parent">
    
        <com.jsibbold.zoomage.ZoomageView
            android:id="@+id/myZoomageView"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:src="@drawable/my_zoomable_image"
            zoomage:restrictBounds="false"
            zoomage:animateOnReset="true"
            zoomage:autoReset="UNDER"
            zoomage:autoCenter="true"
            zoomage:zoomable="true"
            zoomage:translatable="true"
            />
    </RelativeLayout>
```

# License
```
Copyright 2016 Jeffrey Sibbold

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
