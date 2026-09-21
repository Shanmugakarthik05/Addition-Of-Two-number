# ADDITION-OF-TWO-NUMBERS

# AIM

To develop an Android application for the addition of two numbers by accepting two input values from the user and displaying their summation result in a text box.

# ALGORITHM
```
Start the application.
Create two input fields to get the first number and second number from the user.
Create an ADD button to perform the addition.
Read the two numbers entered by the user.
Convert the input values into numeric data.
Add the two numbers using the formula:
Sum = Number 1 + Number 2
Display the calculated sum in the Result text box.
Display the result using a Toast message.
Stop the application.
```
# Developed By:
```
Name: Subbiah S
Reg No:212223220111
```
# activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="24dp"
    android:gravity="center">

    <EditText
        android:id="@+id/num1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter first number"
        android:inputType="numberDecimal" />

    <EditText
        android:id="@+id/num2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter second number"
        android:inputType="numberDecimal" />

    <Button
        android:id="@+id/addButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="ADD"
        android:layout_marginTop="20dp" />

    <EditText
        android:id="@+id/result"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Result"
        android:inputType="numberDecimal"
        android:focusable="false"
        android:layout_marginTop="20dp" />

</LinearLayout>
```

# MainActivity.java

```
package com.example.addition;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText num1, num2, result;
    Button addButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);
        result = findViewById(R.id.result);
        addButton = findViewById(R.id.addButton);

        addButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                String value1 = num1.getText().toString();
                String value2 = num2.getText().toString();

                if (value1.isEmpty() || value2.isEmpty()) {
                    Toast.makeText(MainActivity.this,"Please enter both numbers", Toast.LENGTH_SHORT).show();
                    return;
                }

                double number1 = Double.parseDouble(value1);
                double number2 = Double.parseDouble(value2);

                double sum = number1 + number2;

                result.setText(String.valueOf(sum));

                Toast.makeText(MainActivity.this, "Sum: " + sum, Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

# Output:

<img width="1919" height="1014" alt="Screenshot 2026-08-18 141422" src="https://github.com/user-attachments/assets/f7a05791-a333-4203-9271-9c8af21f9a81" />

# Result:
The Addition of Two Numbers Android application was successfully developed. The application accepts two numbers from the user, calculates their sum, and displays the summation value in the Result text box.
