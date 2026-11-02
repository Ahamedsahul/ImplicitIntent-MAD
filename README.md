# Ex.No:3a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1.Launch the Android application. 

2.Create an Implicit Intent object. 

3.Specify the required action (ACTION_VIEW, ACTION_DIAL, ACTION_SEND, etc.). 

4.Attach the required data using Uri.parse(). 

5.Invoke startActivity() with the Intent. 

6.Android searches for a compatible application. 

7.Display the app chooser if multiple apps are available. 

8.Launch the selected application. 

9.Perform the requested action.

## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: Ahamed Sahul Hameed M
Registeration Number : 212224040016
*/
```
## Mainactivity.java
```java
package com.example.muiexp2a;

import android.content.ActivityNotFoundException;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button button = findViewById(R.id.button);
        EditText editText = findViewById(R.id.editTextText);

        button.setOnClickListener(view -> {
            String input = editText.getText().toString().trim();
            if (input.isEmpty()) {
                editText.setError("Please enter a URL");
                return;
            }
            String finalUrl = input.startsWith("http://") || input.startsWith("https://") ? input : "https://" + input;
            try {
                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(finalUrl));
                startActivity(intent);
            } catch (ActivityNotFoundException e) {
                Toast.makeText(this, "No application found to open this URL", Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```
## activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="148dp"
        android:layout_height="42dp"
        android:text="@string/enter_website"
        android:textSize="24sp"
        app:layout_constraintBottom_toTopOf="@+id/editTextText"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/editTextText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="284dp"
        android:ems="10"
        android:hint="@string/url_hint"
        android:autofillHints="url"
        android:inputType="text"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="144dp"
        android:text="@string/navigate"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## OUTPUT

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/8b8ab46c-798a-46e4-9788-708cbf9ce5cb" />

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/ef2293c2-3daf-4a6d-bccc-55a13fff1d19" />


## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


