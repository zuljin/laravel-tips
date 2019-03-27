### Unsigned Integer
For foreign key migrations instead of <b>integer()</b> use <b>unsignedInteger()</b> type or <b>integer()->unsigned()</b>, otherwise you may get SQL errors.
```
Schema::create('employees', function (Blueprint $table) {
  $table->unsignedInteger('company_id');
  $table->foreign('company_id')->references('id')->on('companies');
  // ...
});
```
