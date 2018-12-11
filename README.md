# Why I like Django and why I like SAP


Django: A web-framework written in the programming language Python. It is open source

SAP (Netweaver): A technology of the software company SAP SE, and the technical foundation for many SAP applications.

In the following text I use the term "SAP" and mean "SAP Netweaver". That's how people it meet talk. The term "Netweaver" is hardly ever used.

SAP gives me the felling: "do not be afraid of creating new tables", since there already several thousand tables, in SAP.


Django has a really great error-debug-page: You see the stacktrace and all local variables of each frame/line in the stacktrace. That's really great. I would like to see this in SAP: https://stackoverflow.com/questions/53595739/pyrfc-sap-get-stacktrace-of-error-not-just-a-message


SELECT ... FROM @itab: I think it very cool that in ABAP you can execute SQL on a tabular variable. You can run a SQL statement on something which is not your database, but just in the memory of the interpreter. Great! https://help.sap.com/doc/abapdocu_752_index_htm/7.52/en-US/abapselect_itab.htm This allows you to avoid loops and practice "thinking in sets".

I like reading the docs of Python and Django. They are short and clean. And in most cases you understand it immediately.
That's different with the docs of SAP. The are complicated. I do not like to read them (too much text).
Maybe I feel this way because I am familiar with Python and Django. I am new to sap. Maybe it is just a biased feeling. Maybe not.

The built-in data types (list, tuples, dictionaries, sets) are great in Python. The same is possible with abap, but you need more typing: https://stackoverflow.com/questions/53613063/dictionaries-in-abap


Unittesting and checking code coverage is daily business in Python and Django projects. In abap this is not that widespread. Maybe I am biased. This is my personal perception.

When I switched from other languages to python in the year 2001 I did this, because Python did show me a stacktrace, if something was wrong.
A stacktrace contains exactly the valuable information which I need to find the root of a problem soon. Often I don't need to start debugging. A stacktrace helps much more than a plain error message. Unfortunately this is not directly visible in ABAP.
In ABAP you get a short-dump which contains a lot of nice data. But you need to consult tcode st22 to see the details. On the other hand this dump contains more information than a stacktrace (for example the content of local variables). 
Related: https://stackoverflow.com/questions/53595739/pyrfc-sap-get-stacktrace-of-error-not-just-a-message

Docs are available in SAP itself via tcode ABAPDOCU. In Python/Django you can download the docs as HTML files. At least you could in the past. I guess today nobody still downloads docs. Most developers have a permanent and fast internet connection.

Both Django/Python and SAP are open source. That was a joke. SAP is not open source, but it has "accesible code". You can view and debug ABAP inside SAP. That's different if you compare this to other ERP vendors. I like this feature. Of course I like open source software with an active community more than commercial software which allows me to look at the code.


I like Django because it is easy to use ForeignKeys which helps you to avoid redundancy. I was surprised that this is different in SAP. See related question: https://stackoverflow.com/questions/53708115/sap-introspection-resolve-foreignkey

I like Django because they do not support [Compound Keys](https://en.wikipedia.org/wiki/Compound_key). Compound keys make thinks much more complicated. In SAP most primary keys are compound keys. I guess this is a reason why foreign keys get used less often in SAP.

