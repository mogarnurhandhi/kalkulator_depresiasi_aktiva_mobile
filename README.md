## *Pengembangan Aplikasi Perhitungan Aktiva Tetap*

pengembangan aplikasi ini berbasis mobile android dengan tools *Android Studio*
dan memakai bahasa Java untuk pengembangan aplikasinya

Adapun tahap tahapnya adalah

1. membuat layut design dari aplikasi tersebut dan disini saya menggunakan constraint layout, coding dilakukan pada file *activity_main.xml*

ini adalah source codenya

```bash
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/dep"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="168dp"
        android:fontFamily="@font/aldrich"
        android:text="DEPRESIASI"
        android:textColor="@color/white"
        android:textSize="20dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/inputN1"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="52dp"
        android:layout_marginEnd="16dp"
        android:background="@drawable/des_bg"
        android:ems="10"
        android:hint="Nilai Perolehan"
        android:inputType="text|number"
        android:paddingLeft="20dp"
        android:paddingTop="13dp"
        android:paddingRight="20dp"
        android:paddingBottom="20dp"
        android:textColor="@color/white"
        android:textColorHint="@color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView" />

    <EditText
        android:id="@+id/inputN2"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:background="@drawable/des_bg"
        android:ems="10"
        android:hint="Nilai Residu"
        android:inputType="text|number"
        android:paddingLeft="20dp"
        android:paddingTop="13dp"
        android:paddingRight="20dp"
        android:paddingBottom="20dp"
        android:textColor="@color/white"
        android:textColorHint="@color/white"
        app:layout_constraintEnd_toEndOf="@+id/inputN1"
        app:layout_constraintStart_toStartOf="@+id/inputN1"
        app:layout_constraintTop_toBottomOf="@+id/inputN1" />

    <EditText
        android:id="@+id/inputN3"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:background="@drawable/des_bg"
        android:ems="10"
        android:hint="Usia Ekonomis"
        android:inputType="text|number"
        android:paddingLeft="20dp"
        android:paddingTop="13dp"
        android:paddingRight="20dp"
        android:paddingBottom="20dp"
        android:textColor="@color/white"
        android:textColorHint="@color/white"
        app:layout_constraintEnd_toEndOf="@+id/inputN2"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="@+id/inputN2"
        app:layout_constraintTop_toBottomOf="@+id/inputN2" />

    <Button
        android:id="@+id/bttnSbmt"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="Proses"
        app:layout_constraintEnd_toEndOf="@+id/inputN3"
        app:layout_constraintStart_toStartOf="@+id/inputN3"
        app:layout_constraintTop_toBottomOf="@+id/inputN3" />

    <TextView
        android:id="@+id/textView3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:fontFamily="@font/aldrich"
        android:text="Hasil Depresiasi"
        android:textColor="@color/white"
        android:textSize="15dp"
        app:layout_constraintEnd_toEndOf="@+id/bttnSbmt"
        app:layout_constraintStart_toStartOf="@+id/bttnSbmt"
        app:layout_constraintTop_toBottomOf="@+id/bttnSbmt" />

    <EditText
        android:id="@+id/outputHsl"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="50dp"
        android:background="@drawable/des_bg"
        android:ems="10"
        android:hint="Hasil"
        android:inputType="text|number"
        android:paddingLeft="20dp"
        android:paddingTop="13dp"
        android:paddingRight="20dp"
        android:paddingBottom="20dp"
        android:textColor="@color/white"
        android:textColorHint="@color/white"
        app:layout_constraintEnd_toEndOf="@+id/bttnSbmt"
        app:layout_constraintStart_toStartOf="@+id/bttnSbmt"
        app:layout_constraintTop_toBottomOf="@+id/bttnSbmt" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_marginTop="56dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:srcCompat="@drawable/logo" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

2. Sedangkan untuk editing bagian border field inputan perlu menambahkan dan mebuat file baru di *drawable* setelah itu buka file tersebut yang ber ekstensi .xml 
adapun source codenya 

```bash
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item>
        <shape>
            <corners android:radius="5dp"/>
            <stroke android:color="@color/white" android:width="2dp" />
        </shape>
    </item>
</selector>
```

3. Untuk fungsionalitas logika aplikasinya pengkodean dilakukan pada file *MainActivity.java* 
adapun implementasi source codenya sebagai berikut

```bash
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item>
        <shape>
            <corners android:radius="5dp"/>
            <stroke android:color="@color/white" android:width="2dp" />
        </shape>
    </item>
</selector>
```

Itu tadi adalah langkah langkah pengembangan aplikasi sederhana untuk menghitung depresiasi aktiva tetap menggunakan tools android studio. 
Dan Hasil ketika dijalankan pada smartphone adalah sebagai berikut
![test](image/test.jpg {width=40px height=100px})


