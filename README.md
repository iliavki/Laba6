# Laba6

Отчет по лабораторной работе №6

1.Создаем проект и добавляем поле EditText тип textMultiLine

2.Добавляем 2 кнопки – Получить данные и сохранить и создаем для них обработчики событий

public void restoreField(View view)
{
TextView nameView = (TextView) findViewById(R.id.saveTextView);
nameView.setText(name);
}

public void saveField(View view)
{ TextView nameBox = (TextView) findViewById(R.id.editTextTextMultiLine);
name = nameBox.getText().toString(); 
}

3. Добавляем поле TextView

Добавим в них код

public class MainActivity extends AppCompatActivity {

String name ="неопределено"; 
final static String nameVariableKey = "NAME_VAR";
final static String textViewTexKey = "TEXT_VIEW"; 
@Override 
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState); 
setContentView(R.layout.activity_main);
} 

@Override 
protected void onSaveInstanceState(Bundle outState) {
outState.putString(nameVariableKey, name); 
TextView nameView = (TextView) findViewById(R.id.saveTextView);
outState.putString(textViewTexKey, nameView.getText().toString()); 
super.onSaveInstanceState(outState);
}

@Override 
protected void onRestoreInstanceState(Bundle savedInstanceState) { 
super.onRestoreInstanceState(savedInstanceState); 
name = savedInstanceState.getString(nameVariableKey); 
String textViewText= savedInstanceState.getString(textViewTexKey); 
TextView nameView = (TextView) findViewById(R.id.saveTextView);
nameView.setText(textViewText); 
} 
}

4. Биндим кнопки на события onClick 
5. Готово 

Резульат работы 


![Lab6 pic1](https://user-images.githubusercontent.com/91713589/143525876-ad179883-6b9b-4b2c-bc29-00f3e8db4d4b.jpeg)
![Lab6 pic2](https://user-images.githubusercontent.com/91713589/143525882-53a4c94a-c8d0-4c84-b948-c97d58afa6e6.jpeg)
![Lab6 pic3](https://user-images.githubusercontent.com/91713589/143525890-7f67a0fa-18da-423e-afbc-7cfcb55fabeb.jpeg)
