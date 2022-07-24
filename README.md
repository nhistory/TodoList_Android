# TodoList_Android

## Add material library

Material is a design system created by Google to help teams build high-quality digital experiences for Android, iOS, Flutter, and the web.

Material Components for Android is available through Google's Maven Repository. To use it:
```
dependencies {
    // ...
    implementation 'com.google.android.material:material:<version>'
    // ...
  }
```
And click the ```sync now``` link on android studio application.

## Build application UI

On the android studio project, we can make our own UI components with ```app/res/layout/activity_main.xml```. eXtensible Markup Language, or XML: A markup language created as a standard way to encode data in internet-based applications. Android applications use XML to create layout files. Unlike HTML, XML is case-sensitive, requires each tag be closed, and preserves whitespace.

### 1. Modify activity_main.xml

You can drag and drop ```recyclerView``` into layout with ```Design``` mode.

<img width="654" alt="image" src="https://user-images.githubusercontent.com/39740066/180631113-3937717c-baa3-42b1-b078-36fefd68c2bb.png">

And change into ```Split``` mode, we can see xml editor and components simultaneously. Each of elements have their own tag with id, layout_width, layout_height, layout_constraint[...].

- Todo items: recycler view
```xml
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/rvTodoItems"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        app:layout_constraintBottom_toTopOf="@+id/btnAddTodo"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
```

- Todo Title: EditText
```xml
    <EditText
        android:id="@+id/etTodoTitle"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="Enter Todo Title"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@+id/btnAddTodo"
        app:layout_constraintStart_toStartOf="parent" />
```

- Add, Delete Button: Button
```xml
    <Button
        android:id="@+id/btnAddTodo"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Add Todo"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@+id/btnDeleteDoneTodos" />

    <Button
        android:id="@+id/btnDeleteDoneTodos"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Delete Done"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />
```

What is dp?
One dp is a virtual pixel unit that's roughly equal to one pixel on a medium-density screen (160dpi; the "baseline" density). Android translates this value to the appropriate number of real pixels for each other density.

### 2. Add item_todo.xml

Make another xml file inside of ```layout``` folder, ```item_todo.xml```. It contains todo items and checkbox.

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="80dp"
    android:paddingStart="8dp"
    android:paddingEnd="8dp">

    <TextView
        android:id="@+id/tvTodoTitle"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Example"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@+id/cbDone"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <CheckBox
        android:id="@+id/cbDone"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

What is ```sp``` stands for?
When defining text sizes, however, you should instead use scalable pixels (sp) as your units (but never use sp for layout sizes). The sp unit is the same size as dp, by default, but it resizes based on the user's preferred text size.

## References
- https://www.youtube.com/watch?v=BBWyXo-3JGQ
