# PHPHandling_ArrayData
PHP handling array data idea

```PHP
extract(['key_is_variable' => 'then_value_as_result' ]);

// Usage: 
echo $key_is_variable
// Output
then_value_as_result

# Instances 
// create a function require file2 inside of it where the variable set from index file is being use.
function getData() { require __DIR__ . 'file2.php'; } 
file2.php < GET : echo $key_is_variable >
index.php < SET : $key_is_variable = then_value_as_result; >
          < USE : getData(); >
// Result
undefined variable: $key_is_variable; 

Solution : 
function getData( $data = [] ) 
{ 

extract($data); // use extract handling array php function

require __DIR__ . 'file2.php'; 

}
file2.php < GET : echo $key_is_variable >
index.php < SET : $key_is_variable = then_value_as_result; >
          < USE : getData([ 'key_is_variable' => 'then_value_as_result' ]); > // the key $key_is_variable become a variable then will execute the value!
// Result
string "then_value_as_result";

Reference: https://www.php.net/manual/en/function.extract.php

```
