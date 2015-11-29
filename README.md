MyToast
=======
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-MyToast-green.svg?style=flat)](https://android-arsenal.com/details/1/2849)

Custom Toast on Android

Image Result
-----

![Capture Project](http://i43.tinypic.com/spaio9.png)


Usage
-----

```java
MyToast.show(this, "MyToast Sample", true);
```

Create
-----

**toast_layout.xml** :
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:background="@drawable/toast_border"
    android:orientation="horizontal"
    android:padding="10dp" >

    <ImageView
        android:id="@+id/toast_image"
        android:layout_width="wrap_content"
        android:layout_height="fill_parent"
        android:contentDescription="@string/app_name"
        android:layout_marginRight="10dp" />

    <TextView
        android:id="@+id/toast_text"
        android:layout_width="wrap_content"
        android:layout_height="fill_parent"
        android:gravity="center"
        android:textColor="@color/White" />

</LinearLayout>
```

**MyToast.java** :
```java
package com.mikhaellopez.mytoast;

import android.content.Context;
import android.view.Gravity;
import android.view.LayoutInflater;
import android.view.View;
import android.widget.ImageView;
import android.widget.TextView;
import android.widget.Toast;

public class MyToast {
    public static void show(Context context, String text, boolean isLong) {
        LayoutInflater inflater = LayoutInflater.from(context);
        View layout = inflater.inflate(R.layout.toast_layout, null);

        ImageView image = (ImageView) layout.findViewById(R.id.toast_image);
        image.setImageResource(R.drawable.ic_launcher);

        TextView textV = (TextView) layout.findViewById(R.id.toast_text);
        textV.setText(text);

        Toast toast = new Toast(context);
        toast.setGravity(Gravity.CENTER, 0, 0);
        toast.setDuration((isLong) ? Toast.LENGTH_LONG : Toast.LENGTH_SHORT);
        toast.setView(layout);
        toast.show();
    }
}
```
