# Why I like Django and why I like SAP

## Introduction

Django: A web-framework written in the programming language Python. It is open source

SAP (Netweaver): A technology of the software company SAP SE, and the technical foundation for many SAP applications.

You can't compare both. Django/Python/PostgreSQL are bricks and SAP is a building. Let's compare them, ignoring the fact, that you can't compare them :-)

In the following text I use the term "SAP" and mean "SAP Netweaver". That's how people I meet talk. The term "Netweaver" is hardly ever used.

## SAP: A lot of tables

SAP gives me the felling: "do not be afraid of creating new tables", since there already several thousand tables, in SAP. I like this.

## Django Debug Page

Django has a really great error-debug-page: You see the stacktrace and all local variables of each frame/line in the stacktrace. That's really great. I would like to see this in SAP: https://stackoverflow.com/questions/53595739/pyrfc-sap-get-stacktrace-of-error-not-just-a-message

## SAP: SQL on data in Memory

SELECT ... FROM @itab: I think it is great that in ABAP you can execute SQL on a tabular variable. You can run a SQL statement on something which is not your database, but just in the memory of the interpreter. Great! https://help.sap.com/doc/abapdocu_752_index_htm/7.52/en-US/abapselect_itab.htm This allows you to avoid loops and practice "thinking in sets".

## Python/Django/PostgreSQL docs are great

I like reading the docs of Python and Django. They are short and clean. And in most cases you understand it immediately.
That's different with the docs of SAP. The are complicated. I do not like to read them (too much text). The SAP docs are bloated, it
is hard to find simple code examples. Maybe I feel this way because I am familiar with Python and Django. I am new to sap. Maybe it is just a biased feeling. Maybe not.

In SAP/ABAP world it is common to get docs from blogs. I think this is dangerous. Blog posts don't get maintained. Docs need to be come from upstream. In this case sap. If the upstream does not provide good docs (including easy to understand examples), then there will be chaos. Some docs here, some docs there and most of the updated and unmaintained. 

## Python: A lot of useful data types

The built-in data types (list, tuples, dictionaries, sets) are great in Python. The same is possible with abap, but you need more typing: https://stackoverflow.com/questions/53613063/dictionaries-in-abap

## Python: Testing is more common

Unittesting and checking code coverage is daily business in Python and Django projects. In abap this is not that widespread. Maybe I am biased. This is my personal perception.

## Python: I like the stacktrace

When I switched from other languages to python in the year 2001 I did this, because Python did show me a stacktrace, if something was wrong.
A stacktrace contains exactly the valuable information which I need to find the root of a problem soon. Often I don't need to start debugging. A stacktrace helps much more than a plain error message. Unfortunately this is not directly visible in ABAP.
In ABAP you get a short-dump which contains a lot of nice data. But you need to consult tcode st22 to see the details. On the other hand this dump contains more information than a stacktrace (for example the content of local variables). 
Related: https://stackoverflow.com/questions/53595739/pyrfc-sap-get-stacktrace-of-error-not-just-a-message

## SAP: Short dumps

I like short-dumps made by SAP. They often contain a hint. This hint suggest what could be the root of the problem and they try to provide a possible solution. Sometimes this hint helps. Often it is wrong. Nevertheless I like the intention: We (the people who create the system) want to help you. I like this spirit.

## Python/Django/PostgreSQL are open source

Both Django/Python and SAP are open source. That was a joke. SAP is not open source, but it has "accesible code". You can view and debug ABAP inside SAP. That's different if you compare this to other ERP vendors. I like this feature. Of course I like open source software with an active community more than commercial software which allows me to look at the code.


## SAP: You can access all tables

In SAP all tables are accesible via se16n. In Django only the tables which were explicitly made accessible (via admin interface) can be seen.

Of course tools like https://www.pgadmin.org/ exist to make every table available.

## Django uses foreign-keys

I like Django because it is easy to use ForeignKeys which helps you to avoid redundancy. I was surprised that this is different in SAP. See related question: https://stackoverflow.com/questions/53708115/sap-introspection-resolve-foreignkey


## Django: No compound keys

I like Django because they do not support [Compound Keys](https://en.wikipedia.org/wiki/Compound_key). Compound keys make thinks much more complicated. In SAP most primary keys are compound keys. I guess this is a reason why foreign keys get used less often in SAP.

## SAP: Row-based permissions are solved 
Row-based permissions are solved in SAP. In Django this is not solved.

## SAP: Tabular data

Displaying tabular data in SAP is very nice. You can click on the heading of a column and in the popup-window you can enter expressions to filter the data. This works mostly everywhere. In Django admin you can use [list_filter](https://docs.djangoproject.com/en/2.1/ref/contrib/admin/#django.contrib.admin.ModelAdmin.list_filter). But this has drawbacks: First, you need to write python code to enable this. Next: you need to enable it for every column. The django admin solution is nice if you do not have many choices, but if you have thousand of choices, the django admin displays all of them in one HTML page. This does not scale.

## Python: Test coverage

Both provide ways to do see the code coverage of tests: https://blogs.sap.com/2014/09/26/code-coverage-based-testing-2/

## Linux/SAP: inspect running processes

On Linux you use the command line tool "top" to see the processes. On SAP sm50. 

##  Django/Python/Postgres: Integers are integers

I like Django/Python/Postgres because they work with integers in a sane way regarding leading zeros. In SAP leading zeros are really crazy. You see a number like "1234" on the screen. If you run an SQL statement "where my_column = 1234" you might not get a result, because in the database a string like "00000001234" is stored. That's why I like Django/Python/Postgres according to this aspect.

##  Django/Python/Postgres: Support for booleans

I like Python and the Django-ORM because they have sane ways to handle boolean values True and False. In ABAP boolean does not exist. Quoting the docs (looks like a joke, but it is not): "ABAP does not yet support Boolean data types and thus does not support data objects for truth values. Therefore, the result of a logical expression cannot be assigned directly to a data object. " https://help.sap.com/doc/abapdocu_752_index_htm/7.52/en-US/abendataobjects_true_value_guidl.htm Since SAP does not provide a boolean (just abap_bool which is a charater field of lenght 1), there are several hundret custom data types in every sap which re-invent boolean. This slows down development and maybe more important: you loose the fun of developing.
Django supports one sane and simple solution to store booleans in a database: https://docs.djangoproject.com/en/2.1/ref/models/fields/#booleanfield

## Python/Django/PostgreSQL: stable

I like the Python/Django/PostgreSQL stacke because no big change is expected in the future. There will be several small improvements, but no big change which will slow me down. This is different in SAP: Hana will come and nobody really knows what will happen in the future. I like HANA as database. It is fast and I trust that bundling of hardware and software to be rock solid.
But of course I know, that there are other in-memory databases available: https://en.wikipedia.org/wiki/List_of_in-memory_databases .. back to what I like: a lot of continuous little updates - the way Python, Django and PostgreSQL get developed.

## Python/Django/PostgreSQL: Community

I like Python/Django because the community is great. If you think something is wrong you can speak up, and it is likely that you get a reply. If you compare the Stackoverflow tag trend (Python ABAP), then ABAP is even not visible: http://sotagtrends.com/?tags=[python,abap]
SAP has a newsletter called "SAP Community Voice". I am subscribed to it. It contains good articles. But the title does not match. It is not the community voice. It is the voice of advertising. If you want to hear the community ask abap developers if they like the language and the sap environment. I talked to some people doing abap daily. I don't want to cite them here.

## PostgreSQL Data Types

I like Python/Django/PostgreSQL because in the database you have some basic data types like integer, boolean, varchar, text, date, timedelta.... You usually do not create custom data types. In SAP you almost always need custom data elements. They are not new data types at database level. Custom data elements are something between the db and your code. I think they make live more complicated. I think they do not help much. I want **tables** and use Foreign-Keys to rows in this tables. I don't need a data element like "invoice-number".
Related: https://www.postgresql.org/docs/current/datatype.html


## Python has a great standard library (json)

Libraries which have proven to be reliable and useful for many developers might get incoporated into the python standard library.
This is great, since this way you have source code which is supported and gets bug fixes. And it is canonical. There are not ten libraries, no there is one implemetentation.

You want to convert to create json from ABAP? Yes, it is possible. But there are too many ways. See: https://stackoverflow.com/questions/16154293/how-to-encode-json-in-abap Now the developer need to invest time to find the matching library.

In Python it is easy (I love "no brainers"), since there is one lib in the standard library, no need to find the matching lib: https://docs.python.org/3/library/json.html

## URLs for docs do not change.

The URLs for the docs do hardly change in the Python/Django/PostgreSQL world.

The URLs are nice and you could remember them (but my favorite search engine is still faster then my brain).

If I search for sap docs, I often get a "http 404: file not found" error.

That's my impression. I have no numbers to prove this.

## Python: Installing open source libraries is easy.

There are many great open source libraries at: https://pypi.org/
Installing them with the tool `pip` is very easy.

There are some cool open source tools for sap, too. For example ZTOAD: http://quelquepart.biz/article7/ztoad-requeteur-open-sql
But getting it installed in SAP is complicated.

## Linux: simple process and user model.

Linux is great because the process and user model is simple. If you are root, you can debug any process and you can get any local linux user you like.

In ABAP/SAP this is not possible, at least not as simple as in linux:

https://stackoverflow.com/questions/55742890/debugging-as-different-user


## I like debuggging Python Code: I can evaluate code snippets during debugging.

During debugging Python Code (I use PyCharm, but other IDEs support this, too) I can display the content of variables. This works in ABAP (SE80), too.

But in Python I can evaluate small expressions during debugging. For example I can evaluate `len(my_string)`.

Unfortunately this is not possible in ABAP. To get this in ABAP you need to add a new code line (for example `data(my_len) = strlen( my_string )`). And start debugging again.


## With Python/Django/PostgreSQL I can use a very popular programming language

Python is the most loved programming language in the year 2019: https://fossbytes.com/most-loved-hated-programming-languages-2019/

Python feels good.

It is great, that I can calls SAP-RFC with the python library pyRFC. But sever side code needs to be written in ABAP. And the language ABAP is hardly known. 



