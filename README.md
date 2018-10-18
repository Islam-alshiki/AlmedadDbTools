# AlmedadDbTools
small tool to select, insert update and delete from SQL databases

# Methods - Constructors
<ul>
  <li>
    Constructor : public dbConncector(String connStr)
    <p>Takes an String SonnectionString to init the object to use later.<p>
  </li>
      <li>
        Constructor : public dbConncector(SqlConnection con)
<p>Takes an System.Data.SqlClint.SqlConnection to init the object to use later.<p>
        </li>
</ul>
<hr>
# Methods
<ul>
  <li>
    public DataTable getAllFrom(String tableName)
    <p>Takes an String for the table to get all rows and return a System.Data.DataTable object.<p>
  </li>
      <li>
        public DataTable exec(String queiry)
        <p>Takes an String for the queiry and return a System.Data.DataTable object.<p>
      </li>
</ul>
