# Hawk
This is a collection of PHP classes manipulted to easy the difficulties you have when communicating with a MySQL database, trust me you will love this one. Check out detailed tutorials on my YouTube channel

# <b>Summary</b>
This short library do to say is to ease your operation with a MySQL database via PHP.
This will do the 4 basic operations with the database i.e<br/>
<b>INSERT</b><br/>
<b>SELECT</b><br/>
<b>DELETE</b><br/>
<b>UPDATE</b><br/>
<hr/>
<h4>Initialize a database helper class first into your script as shown below</h4>
~~~
  require_once('hawk/DBHelper.php');<br/>
  $dbh = new DBHelper();<br/>
  // alternatively you can use the optimized Database Helper<br/>
  // require_once('hawk/Optimizer.php');<br/>
  // $dbh = new Optimizer();<br/>
~~~
<hr/>
<h5>INSERT OPERATION</h5>
<p>This one inserts data into <b>EVERY</b> table provided your data is matching the columns</p>
~~~
$insertData = [
  'my_table', //the table name
  'first_col_val', //first column value
  'second_col_val' //second column value
  .
  .
  .
  . //the list of values for all columns
]
$inserted = $dbh->insertData($insertData);
~~~
<p>This works for both cases of the DBHelper and returns true on successfully inserting and false on failure
<hr/>
<h5>SELECT</h5>
<p>This selects data with your matching requests and returns an array of results</p>
~~~
$results = $dbh->getDetails(
 'my_table', //the table name
 'col_name', //the name of the column which to match with a certain value
 'col_value' //the value to find in the column mentioned above
);
~~~
<p>There is a whole load of select functions there, just read the documentation on the scripts
NB: this is for the simple database helper, the optimized is a little complex but saves your server memory</p>
<hr/>
<h5>DELETE</h5>
<p>This deletes any data from the table, all you have to put the required column-value details to target rows</p>
~~~
$deleted = $dbh->deleteData(
 'my_table', //the name of the table to make the operation
 'col_name', //the column name where you have to find a match
 'col_value' //the value to match in row so as to delete the row
);
~~~
<p>This returns true on success and false otherise</p>
<hr/>
<h5>UPDATE</h5>
<p>This one updates rows that you target successfully</p>
~~~
$updated = $dbh->updateData(
 'my_table', //the name of the table you want to update in
 'where_column', //the column name you want to target
 'where_value', //the value that`s in the column you wish to target. 
 'set_column', //the column name you wish to update
 'set_value', //the new value you wish to place in the set column
);
~~~
<p>When successfully updated you will get a true, else you get a false</p>
