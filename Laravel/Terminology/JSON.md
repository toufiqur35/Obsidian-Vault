- JSON stands for **J**ava-Script Object Notation.
- JSON is a lightweight data-interchange format that is completely language independent.
- JSON is plain text written in JavaScript object notation
- It is derived from java-script, but many modern programming language include code to generate and parse JSON format data.
- The official internet media type for JSON in application/JSON.
- It is design for human readable data interchange.
- The file name extension is `.json`

#### Bad Special Characters Inside JSON & Solution
* Backspace : Replace with \\b
* Form feed : Replace with \\f
* Newline : Replace with \\n
* Carriage return : Replace with \\r
* Tab : Replace with \\t
* Double quote : Replace with \\"
* Backslash : Replace with \\\

#### Best practices of JSON
* Always enclose the key: Value pair within double quotes.
```
{'id':'1','name':file} is not right
{"id":1,"name":"file"} is okay
{"id":"1","name":"file"} is the best
```

* Never use Hyphens is your Key fields.
```
{"first-name":"toufiqur","last-name":"sobuj"} is not right
{"first_name":"toufiqur","last_name":"sobuj"} is okay
{"firstname":"toufiqur","lastname":"sobuj"} is okay
{"firstName":"toufiqur","lastName":"sobuj"} is the best
```

```
{
  "Students": [
		{ 
			"Name":"Amit Goenka" ,
			"Major":"Physics" 
			}, 
			  { 
			  "Name":"Smita Pallod" ,
		      "Major":"Chemistry" 
		  }, 
			  {
			   "Name":"Rajeev Sen" , 
			   "Major":"Mathematics" 
		}
	]
}

```