# Dynamic SQL
## What is dynamic SQL?
Static SQL is an SQL statement that is completely specified and parsed at compile time.
Dynamic SQL refers to an SQL statement that is *not completely specified* (and cannot be parsed) until the time of execution.

## When you need dynamic SQL?
_Note: You should only use dynamic SQL when you have to use it. If you can write static SQL, you should do it. It's simpler and it's at least a little bit faster._

* Build ad-hoc query and update application
* Excute DDL statement from within PL/SQL
* Soft-code your application code, placing business rules in tables and executing them dynamiclly
* Avoid redundancies in your code

## Two ways to write dynamic SQL
* DBMS_SQL package
* Native dynamic SQL
A new, native implementation of dynamic SQL that does almost all of what DBMS_SQL can do, but much more easily and usually more efficiently.
However, to write native dynamic SQL code, you must know at compile time the number and data types of the input and output variables of the dynamic statement. If you do not know this information at compile time, you must you the DBMS_SQL package.

## Native Dynamic SQL
EXECUTE IMMEDIATE "SELECT .. " (BULK COLLECT) INTO _out-bind variables_ USING _in-bind variables_
EXECUTE IMMEDIATE "INSERT/DELETE/UPDATE .." RETURNING INTO _out-bind variables_ USING _in-bind variables_
EXECUTE IMMEDIATE "BEGIN .. END;" USING _all in&out-bind variables
OPEN _cursor_ FOR "SELECT .." USING _in-bind variables_
