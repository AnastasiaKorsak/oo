dependencies {

    implementation 'androidx.sqlite:sqlite:2.1.0'

}



import android.content.Context;

import android.database.sqlite.SQLiteDatabase;

import android.database.sqlite.SQLiteOpenHelper;



public class DBHelper extends SQLiteOpenHelper {

    private static final String DATABASE_NAME = "mydatabase.db";

    private static final int DATABASE_VERSION = 1;

    private static final String TABLE_NAME = "items";

    private static final String COLUMN_ID = "id";

    private static final String COLUMN_NAME = "name";

    private static final String COLUMN_COST = "cost";

    private static final String COLUMN_NUMBER = "number";



    public DBHelper(Context context) {

        super(context, DATABASE_NAME, null, DATABASE_VERSION);

    }



    @Override

    public void onCreate(SQLiteDatabase db) {

        String createTableQuery = "CREATE TABLE " + TABLE_NAME + "(" +

                COLUMN_ID + " INTEGER PRIMARY KEY AUTOINCREMENT, " +

                COLUMN_NAME + " TEXT, " +

                COLUMN_COST + " TEXT, " +

                COLUMN_NUMBER + " TEXT)";

        db.execSQL(createTableQuery);

    }



    @Override

    public void onUpgrade(SQLiteDatabase db, int oldVersion, int newVersion) {

        String dropTableQuery = "DROP TABLE IF EXISTS " + TABLE_NAME;

        db.execSQL(dropTableQuery);

        onCreate(db);

    }

}







public class Model {

    private String id;

    private String name;

    private String cost;

    private String number;



    public Model(String id, String name, String cost, String number) {

        this.id = id;

        this.name = name;

        this.cost = cost;

        this.number = number;

    }



    public String getId() {

        return id;

    }



    public String getName() {

        return name;

    }



    public String getCost() {

        return cost;

    }



    public String getNumber() {

        return number;

    }

}











Import androidx.appcompat.app.AppCompatActivity;

Import android.content.Intent;

Import android.os.Bundle;

Import android.view.View;

Import android.widget.Button;

Import androidx.recyclerview.widget.LinearLayoutManager;

Import androidx.recyclerview.widget.RecyclerView;

Import java.util.ArrayList;

Import java.util.List;



Public class MainActivity extends AppCompatActivity {



    Private RecyclerView recyclerView;

    Private RecyclerView.Adapter adapter;

    Private List<Model> modelList;

    Private Button addButton;



    @Override

    Protected void onCreate(Bundle savedInstanceState) {

        Super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);



        recyclerView = findViewById(R.id.recycler_view);

        recyclerView.setHasFixedSize(true);

        recyclerView.setLayoutManager(new LinearLayoutManager(this));



        modelList = new ArrayList<>();



        // TODO: Получение данных из базы данных и добавление их в modelList



        Adapter = new MyAdapter(modelList);

        recyclerView.setAdapter(adapter);



        addButton = findViewById(R.id.add_button);

        addButton.setOnClickListener(new View.OnClickListener() {

            @Override

            Public void onClick(View v) {

                Intent intent = new Intent(MainActivity.this, AddActivity.class);

                startActivityForResult(intent, 1);

            }

        });

    }



    @Override

    Protected void onActivityResult(int requestCode, int resultCode, Intent data) {

        Super.onActivityResult(requestCode, resultCode, data);



        If (requestCode == 1 && resultCode == RESULT_OK) {

            // Обновление списка с использованием новых данных из второго экрана

        }

    }

}











Import androidx.appcompat.app.AppCompatActivity;

Import android.content.Intent;

Import android.os.Bundle;

Import android.view.View;

Import android.widget.Button;

Import android.widget.EditText;



Public class AddActivity extends AppCompatActivity {



    Private EditText nameEditText;

    Private EditText costEditText;

    Private EditText numberEditText;

    Private Button addToDBButton;



    @Override

    Protected void onCreate(Bundle savedInstanceState) {

        Super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_add);



        nameEditText = findViewById(R.id.name_edit_text);

        costEditText = findViewById(R.id.cost_edit_text);

        numberEditText = findViewById(R.id.number_edit_text);



        addToDBButton = findViewById(R.id.add_to_db_button);

        addToDBButton.setOnClickListener(new View.OnClickListener() {

            @Override

            Public void onClick(View v) {

                String name = nameEditText.getText().toString();

               











# oo
