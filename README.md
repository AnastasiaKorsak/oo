<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".AddActivity">

    <EditText
        android:id="@+id/name_edit_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="16dp"
        android:hint="Name"
        android:inputType="text" />

    <EditText
        android:id="@+id/cost_edit_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="16dp"
        android:hint="Cost"
        android:inputType="number" />

    <EditText
        android:id="@+id/number_edit_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="16dp"
        android:hint="Number"
        android:inputType="number" />

    <Button
        android:id="@+id/add_to_db_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_margin="16dp"
        android:text="Add to Database"
        android:textColor="@android:color/white"
        android:background="@android:color/holo_blue_light" />

</LinearLayout>
