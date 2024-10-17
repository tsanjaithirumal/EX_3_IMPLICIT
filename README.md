## EXPERIMENT:03  Implement an application that uses Intent(Implicit) using Android Studio.
Design an Android application with a text field and an "Open in Browser" button. On pressing the button, the app should fetch the URL from the text field and open it in a browser using an Implicit Intent.

## AIM:

To design an Android application with a TextField and a button labeled "Open in Browser." Upon pressing the button, the application should retrieve the URL entered in the TextField and open it in the device's web browser using an implicit intent.
## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:


1. **Start Android Studio**: Create a new project with an empty activity.

2. **Add UI Elements**: In `activity_main.xml`, add a `TextField` (EditText) for entering the URL and a Button labeled "Open in Browser".

3. **Handle Button Click**: In `MainActivity.java` or `MainActivity.kt`, set an `OnClickListener` for the button.

4. **Retrieve URL**: On button click, retrieve the text entered in the `TextField`.

5. **Check URL**: Ensure the URL is valid and starts with "http://" or "https://".

6. **Create Implicit Intent**: Create an implicit intent using `Intent.ACTION_VIEW` and pass the URL.

7. **Start Activity**: Use `startActivity(intent)` to open the URL in the device's browser.

8. **Test the Application**: Run the app on an emulator or physical device.

9. **End**: Application successfully opens URLs in the browser.



## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by:SANJAI T
Registeration Number : 212222040145
*/
```
## MainActivity.java:
```

package com.example.ex_3;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    Button button;

    EditText editText;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        final EditText editText = (EditText) findViewById(R.id.urlText);
        Button btn = (Button) findViewById(R.id.btnNavigate);
        btn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String url = editText.getText().toString();
                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
                startActivity(intent);
            }
        });
    }
}


```

## Activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/urlText"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="100dp"
        android:ems="10" />
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/btnNavigate"
        android:layout_below="@+id/urlText"
        android:text="Navigate"
        android:layout_centerHorizontal="true" />
</RelativeLayout>
```




## OUTPUT

![Screenshot 2024-09-14 132053](https://github.com/user-attachments/assets/2b5f0a8b-6913-4f99-80d5-2471dac38a62)





## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the web page using Android Studio was developed and executed successfully.
