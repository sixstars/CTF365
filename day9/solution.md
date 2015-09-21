# Day9 Solution

------

Since php is weak typing, some comparings maybe not safe enough.

First, ```if (0 >= preg_match('/^[[:graph:]]{12,}$/', $password))``` requires that the length of password must equals or is bigger than 12 and no blank space or TAB(see [:graph:]).
Second, ```if (6 > preg_match_all($reg, $password, $arr))``` means that the count of string whose value is punct/digit/upper/lower is equal to or more than 6.

Third, 
```php
$ps = array('punct', 'digit', 'upper', 'lower');
foreach ($ps as $pt){    
    if (preg_match("/[[:$pt:]]+/", $password))    
        $c += 1;    
    }    
if ($c < 3)
    break;
```
requires that the password must contains 3 or more types in punct/digit/upper/lower.

And at last, the password must equals 42.

To satisify the first requirement, it's easy to give the following answer:
`+42.0000000000`

To satisify the second and the third requirements,you can use some tricks:
`420.00000000e-1`
`+4.20000000000e1`

When `==` is used to compare a number and a string, PHP will convert the string to number and then do comparing job. If you want to do this job safer, please use ```===```.

Some links:

http://stackoverflow.com/questions/80646/how-do-the-php-equality-double-equals-and-identity-triple-equals-comp
