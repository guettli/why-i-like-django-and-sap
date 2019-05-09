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

If a enter "foo_method python" (with "foo_method" being a method of the standard library of python), my favorite search engine provides the canonical page for this method on the top. 

If I search for "foo_method abap" (with "foo_method" being a method of the standard library of abap), my favorite search engine does provide a lot of blog entries (some of them are outdated). The canonical URL for the documentation of this method, seems to not be missing. You can read docs via SAP-GUI, but docs like this (non-online docs, just available via the custom native GUI) are not state of the art. 

Some of the SAP docs are not available online. For example "SAP NetWeaver Remote Function Call (RFC) Software Development Kit (SDK)" can be downloaded here https://support.sap.com/en/product/connectors/nwrfcsdk.html#section_1291717368
This means I can't find this content if I use my favorite search engine, since my favorite search engine does index only web pages which are available online, not my local disk.

I want to know the maximum size of xstring. The datatype xstring is like bytes in Python, it is made to contain binary data.
If you google for "max length xstring abap" you results pointing to form posts. None of them points to the canonical upstream docs. That's all "according to hearsay", it is guessing (something you should avoid in information technology).

## SAP Notes are never part of a google search result

SAP notes are only visible if you have login for the "SAP ONE Support Launchpad". This means you favorit search engine can't index them.
Users can't create hyperlinks to the sap notes in Q+A sites. You just can copy+paste the number.
I have a login to the sap notes. That's not the problem. But the current situation is not easy, not convenient, not simple, not straight forward.




## URLs for docs do not change.

The URLs for the docs do hardly change in the Python/Django/PostgreSQL world.

The URLs are nice and you could remember them (but my favorite search engine is still faster then my brain).

If I search for sap docs, I often get a "http 404: file not found" error.

That's my impression. I have no numbers to prove this.


## Python: A lot of useful data types

The built-in data types (list, tuples, dictionaries, sets) are great in Python. The same is possible with abap, but you need more typing: https://stackoverflow.com/questions/53613063/dictionaries-in-abap


##  Django/Python/Postgres: Integers are integers

I like Django/Python/Postgres because they work with integers in a sane way regarding leading zeros. In SAP leading zeros are really crazy. You see a number like "1234" on the screen. If you run an SQL statement "where my_column = 1234" you might not get a result, because in the database a string like "00000001234" is stored. That's why I like Django/Python/Postgres according to this aspect.

##  Django/Python/Postgres: Support for booleans

I like Python and the Django-ORM because they have sane ways to handle boolean values True and False. In ABAP boolean does not exist. Quoting the docs (looks like a joke, but it is not): "ABAP does not yet support Boolean data types and thus does not support data objects for truth values. Therefore, the result of a logical expression cannot be assigned directly to a data object. " https://help.sap.com/doc/abapdocu_752_index_htm/7.52/en-US/abendataobjects_true_value_guidl.htm Since SAP does not provide a boolean (just abap_bool which is a charater field of lenght 1), there are several hundret custom data types in every sap which re-invent boolean. This slows down development and maybe more important: you loose the fun of developing.
Django supports one sane and simple solution to store booleans in a database: https://docs.djangoproject.com/en/2.1/ref/models/fields/#booleanfield


## PostgreSQL Data Types

I like Python/Django/PostgreSQL because in the database you have some basic data types like integer, boolean, varchar, text, date, timedelta.... You usually do not create custom data types. In SAP you almost always need custom data elements. They are not new data types at database level. Custom data elements are something between the db and your code. I think they make live more complicated. I think they do not help much. I want **tables** and use Foreign-Keys to rows in this tables. I don't need a data element like "invoice-number".
Related: https://www.postgresql.org/docs/current/datatype.html


## Python has a great standard library (json)

Libraries which have proven to be reliable and useful for many developers might get incoporated into the python standard library.
This is great, since this way you have source code which is supported and gets bug fixes. And it is canonical. There are not ten libraries, no there is one implemetentation.

You want to convert to create json from ABAP? Yes, it is possible. But there are too many ways. See: https://stackoverflow.com/questions/16154293/how-to-encode-json-in-abap Now the developer need to invest time to find the matching library.

In Python it is easy (I love "no brainers"), since there is one lib in the standard library, no need to find the matching lib: https://docs.python.org/3/library/json.html


## Python: Testing is more common

Unittesting and checking code coverage is daily business in Python and Django projects. In abap this is not that widespread. Maybe I am biased. This is my personal perception.

## Python: Test coverage

Both provide ways to do see the code coverage of tests: https://blogs.sap.com/2014/09/26/code-coverage-based-testing-2/

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

I like Django because it is easy to use ForeignKeys which helps you to avoid redundancy.
I was surprised that this is different in SAP.

See related question: https://stackoverflow.com/questions/53708115/sap-introspection-resolve-foreignkey


## SAP: Column MANDT ... mistake

I think it is a design mistake to share the tables between sytems like SAP does it.

If you login with the SAPGUI you need to supply a client (Mandant). 
Everything you see and do operates
only on a subset of all tables. The user must only see and alter rows of the matching MANDT.

This makes things much more complicated.

It makes sense to have several stages: DEV, QUAL, PROD

It makes sense to be able to run several systems on the same hardware.

But the MANDT column makes more trouble than it solves. 

## Django: No compound keys

I like Django because they do not support [Compound Keys](https://en.wikipedia.org/wiki/Compound_key).

Compound keys make thinks much more complicated. 
In SAP most primary keys are compound keys (almost all tables have the column MANDT). 
I guess this is a reason why foreign keys get used less often in SAP.



## SAP: Row-based permissions are solved 

Row-based permissions are solved in SAP. In Django this is not solved. At least not in Django core.

You have several ways to walk around this in Django: ModelAdmin.get_queryset(), Garidan (performance can be get a problem), use only custom views.

## SAP: Tabular data

Displaying tabular data in SAP is very nice (ALV Grid). You can click on the heading of a column and in the popup-window you can enter expressions to filter the data. This works mostly everywhere. In Django admin you can use [list_filter](https://docs.djangoproject.com/en/2.1/ref/contrib/admin/#django.contrib.admin.ModelAdmin.list_filter). But this has drawbacks: First, you need to write python code to enable this. Next: you need to enable it for every column. The django admin solution is nice if you do not have many choices, but if you have thousand of choices, the django admin displays all of them in one HTML page. This does not scale.


## Linux/SAP: inspect running processes

On Linux you use the command line tool "top" to see the processes. On SAP sm50. 

## Python/Django/PostgreSQL: stable

I like the Python/Django/PostgreSQL stacke because no big change is expected in the future. There will be several small improvements, but no big change which will slow me down. This is different in SAP: Hana will come and nobody really knows what will happen in the future. I like HANA as database. It is fast and I trust that bundling of hardware and software to be rock solid.
But of course I know, that there are other in-memory databases available: https://en.wikipedia.org/wiki/List_of_in-memory_databases .. back to what I like: a lot of continuous little updates - the way Python, Django and PostgreSQL get developed.

## Python/Django/PostgreSQL: Community

I like Python/Django because the community is great. If you think something is wrong you can speak up, and it is likely that you get a reply. If you compare the Stackoverflow tag trend (Python ABAP), then ABAP is even not visible: http://sotagtrends.com/?tags=[python,abap]
SAP has a newsletter called "SAP Community Voice". I am subscribed to it. It contains good articles. But the title does not match. It is not the community voice. It is the voice of advertising. If you want to hear the community ask abap developers if they like the language and the sap environment. I talked to some people doing abap daily. I don't want to cite them here.

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

Here is the work-around to see the ending of a huge string during debugging with abap: https://stackoverflow.com/questions/55844508/show-the-end-of-a-big-string-during-debugging

## With Python/Django/PostgreSQL I can use a very popular programming language

Python is the most loved programming language in the year 2019: https://hired.com/page/state-of-software-engineers/hottest-coding-languages/#most-loved-languages

Python feels good.

It is great, that I can calls SAP-RFC with the python library pyRFC. But sever side code needs to be written in ABAP. And the language ABAP is hardly known. 

Young people which have finished there education and look at several job opportunities have the choice. Their choice is important and money is only one small part of the decission. They choose what they like. They choose what they are familiar with. 

Releasing the interpreters, compilers, libraries and related tools as open source was a clever decision by google, microsoft and other big players.

Looking at above list of languages: ABAP is not even mentioned.

For google it will be easy to find people familiar with open source languages like Python, Go or TypeScript.

StackOverflow has 2k question with tag "abap" and 1M question with tag "python".

## I like Python/Django/PostgreSQL: git

With the Python/Django/PostgreSQL stack I can use any version control system which I like. And I like git.

SAP (se80) has a built in version control. It works for most cases. But I prefer git: it has more features and I find more usefull docs via my favorite search engine.

## I like current web solutions: libraries for clients are 100% open source.

In most cases the libraries for accessing services are mostly 100% open source. For example the libraries to access amazon services are 100% open source.

For PyRFC (the Python librarie to access SAP via their custom RFC protocol) is 50% open source. The part on github is open source.

But you need the closed source:

> SAP NW RFC SDK C++ binaries must be downloaded (SAP partner or customer account required) 

This slows down developement. The company I work for is a SAP partner. But nevertheless this fact makes things more complicated:

* I need to build a custom package since "SAP NW RFC SDK C++ binaries" are not freely redistributable. Other libraries (to closed source services) like boto for s3 can get downloaded from pypi.

* I want to use a new version of pyRFC: I need build our custom python package again. Now I need find my password to get to the new libraries for a custom sap page .... grrr

## I like Python since a string can contain a '\0'

In C a string gets terminated by the `\0` (null byte). This means strings in C can not contain this character,
except you do your own string handling and always keep track of the lenght of the string yourself.

In ABAP it is the same. A `string` gets terminated by a `\0`.

I like Python because a string can contain a `\0`.

Usually you don't want this. If your data contains a `\0` then it is binary data, not a string.

This means in ABAP you should use `xstring` and in Python `bytes`.

But nevertheless it is nice that a string in Python does not get terminated by the null byte.


