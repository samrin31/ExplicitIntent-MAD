# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1.Start the project: Create a new Android project with two Empty Activities (MainActivity and MainActivity2).

2.Design the First Screen: In activity_main.xml, add an EditText to receive the number input and a Button to trigger the calculation.

3.Design the Second Screen: In activity_main2.xml, add a TextView to display the calculated factorial result.

4.Get Input (MainActivity): Inside MainActivity.java, set an OnClickListener on the button to retrieve the entered number from the EditText.

5.Pass Data using Explicit Intent: Create an Intent targeting MainActivity2.class. Attach the entered number to the intent using intent.putExtra(), and start the activity using startActivity(intent).

6.Receive Data (MainActivity2): In MainActivity2.java, use getIntent().getStringExtra() (or getIntExtra()) to retrieve the passed number.

7.Calculate Factorial: Write a loop or recursive function to compute the factorial of the received number.

8.Display Result: Update the TextView in the second activity to show the computed factorial value.

9.Stop: Run and test the application.

## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by:SAMRIN T 
Registeration Number :212225100042
*/
```
## MAINACTIVITY.JAVA
~~~
package com.example.activity;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    EditText editText;
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        editText = findViewById(R.id.editTextText);
        button = findViewById(R.id.button);
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String num = editText.getText().toString();
                Intent intent = new Intent(MainActivity.this, MainActivity2.class);
                intent.putExtra("number", num);
                startActivity(intent);
            }
        });
    }
}
~~~
## ACTIVITY_MAIN.XML
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="126dp"
        android:layout_height="23dp"
        android:text="Enter a Number"
        android:textSize="18sp"
        app:layout_constraintBottom_toTopOf="@+id/editTextText"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.698" />

    <EditText
        android:id="@+id/editTextText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="144dp"
        android:ems="10"
        android:inputType="text"
        android:text=""
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="232dp"
        android:text="FIND FACTORIAL"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.505"
        app:layout_constraintStart_toStartOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
## MAINACTIVITY2.JAVA
```
package com.example.activity;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.TextView;

public class MainActivity2 extends AppCompatActivity {
    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);
        result = findViewById(R.id.result);
        String number = getIntent().getStringExtra("number");
        if (number != null && !number.isEmpty()) {
            try {
                int n = Integer.parseInt(number);
                long fact = 1;
                for (int i = 1; i <= n; i++) {
                    fact = fact * i;
                }
                result.setText("Factorial of " + n + " = " + fact);
            } catch (NumberFormatException e) {
                result.setText("Invalid input");
            }
        }
    }
}
```
## ACTIVITY_MAIN2.XML
```
<?xml version="1.0" encoding="utf-8"?>

<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/result"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Factorial"
        android:textSize="30sp"
        android:textStyle="bold"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```

## OUTPUT
<img width="1051" height="565" alt="Screenshot 2026-11-24 123700" src="https://github.com/user-attachments/assets/453e91f1-4636-448b-ac33-f6e72dabbd86" />
<img width="1047" height="560" alt="Screenshot 2026-11-24 123719" src="https://github.com/user-attachments/assets/753c94c2-839a-49a5-a795-dfcaacbeebde" />
<img width="1053" height="557" alt="Screenshot 2026-11-24 123731" src="https://github.com/user-attachments/assets/7fad796a-ab29-4c48-af69-2bcc364e2cbd" />

## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.


