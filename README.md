# AlmedadDbTools
small tool to select, insert update and delete from SQL databases

# dbConncector Methods - Constructors
<ul>
  <li>
    Constructor : public dbConncector(String connStr)
    <p>Takes an String SonnectionString to init the object to use later.<p>
    
    ``` csharp
      String ConnectionStrong = "";
      dbConncector db = new dbConncector(ConnectionStrong);
    ```
    
</li>
<li>
        Constructor : public dbConncector(SqlConnection con)
<p>Takes an System.Data.SqlClint.SqlConnection to init the object to use later.<p>
  
``` csharp
  sqlConnection con = new sqlConnection();
  dbConncector db = new dbConncector(con);
```
    
  </li>
</ul>

# dbConncector Methods
<ul>
<li>
public DataTable getAllFrom(String tableName)
<p>Takes an String for the table to get all rows and return a System.Data.DataTable object.<p>
  
``` csharp
  dbConncector db = new dbConncector(con);
  DataTable result = db.getAllFrom("tableName");
```
    
  </li>
  <li>
    public DataTable exec(String queiry)
    <p>Takes an String for the queiry and return a System.Data.DataTable object.<p>
    
``` csharp
  dbConncector db = new dbConncector(con);
  DataTable result = db.exec("select * from tableName");
```
    
  </li>
  <li>
    public DataTable getAllFrom(String PeocName, List<Field> filds)
    <p>Takes an String for the table name, and a list of Field object contains the pharametrs with values to get only specific rows and return a System.Data.DataTable object.<p>
    
``` csharp
  // Select from student table the student they live in libya.
  dbConncector db = new dbConncector(con);
  Field v1 = new Field("student_location" , "Libya");
  List<Field> values = new List<Field>();
  values.add(v1);
  DataTable result = db.getAllFrom("student_table" , values);
```
    
  </li>
  <li>
    public int getResultFromSp(String PeocName, List<Field> filds) (Used in stored procedures that insert, update or delete only )
    <p>Takes an String for the stored procedures namem, and a list of Field object contains the pharametrs with values, it's retirn an int as a number of changes in database <p>
  
``` csharp
  // insert new student
  dbConncector db = new dbConncector(con);
  Field v1 = new Field("student_name" , "Islam");
  Field v2 = new Field("student_location" , "Libya");
  List<Field> values = new List<Field>();
  values.add(v1);
  values.add(v2);
  int result = db.getAllFrom("student_table" , values);
```
</li>
</ul>

# class Field use
Before you pass the Field object see this example.

``` csharp
  dbConncector fb = new dbConncector();
  String taegetTable = "sp_login";
  List<Field> fields = new List<Field>();
  fields.Add(new Field("email", "islam.alshiki94@gmail.com")); // pharameter in sp_login  stored procedures
  fields.Add(new Field("password", "123456")); //  pharameter in sp_login  stored procedures
  DataTable tb = fb.getAllFromSp(taegetTable, fields); // 
```
