#### javascdript 删除字符串中第一个和最后一个斜杠

~~~
var string = "/banking/bonifici/italia/";
if (string.charAt(0) == "/") string = string.substr(1);
if (string.charAt(string.length - 1) == "/") string = string.substr(0, string.length - 1);
console.log('string :>> ', string);
~~~
