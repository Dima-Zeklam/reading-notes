# THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS 

## Persistent
### Persistent local storage is one of the areas where native client applications have held an advantage over web applications.

![Persistent](https://diveinto.html5doctor.com/i/aoc-p.png)

### Historically, web applications have had none of these luxuries. Cookies were invented early in the web’s history, and indeed they can be used for persistent local storage of small amounts of data. But they have three potentially dealbreaking downsides:

* Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over.

* Cookies are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)

* Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful.

## INTRODUCING HTML5 STORAGE

### HTML5 Storage 

![HTML5 Storage ](https://srimax.com/wp-content/uploads/2014/04/html5-local-storage-300x171.jpg)


is a specification named Web Storage, which was at one time part of the HTML5 specification proper, but was split out into its own specification for uninteresting political reasons.


### HTML5 STORAGE SUPPORT

IE	|FIREFOX |	SAFARI |	CHROME |	OPERA|	IPHONE |	ANDROID
-----|--------|----------|----------|---------|----------|------------
8.0+ |	3.5+ |	4.0+ |	4.0+  |	10.5+    | 	2.0+	 |2.0+



*check for HTML5 Storage*


```
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}

```

**Instead of writing this function yourself, you can use Modernizr to detect support for HTML5 Storage :**

```
if (Modernizr.localstorage) {
  // window.localStorage is available!
} else {
  // no native support for HTML5 storage :(
  // maybe try dojox.storage or a third-party solution
}
```

## USING HTML5 STORAGE
HTML5 Storage is based on named **key/value** pairs. You store data based on a named key, then you can retrieve that data with the same key. The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats. However, the data is actually stored as a string. If you are storing and retrieving anything other than strings, you will need to use functions like `parseInt()` or `parseFloat()` to coerce your retrieved data into the expected JavaScript datatype.

## STORAGEEVENT OBJECT

PROPERTY |	TYPE	|DESCRIPTION
--------|----------|-----------
key	 |string |	the named key that was added, removed, or modified
old  |Value|  any	the previous value (now overwritten), or null if a new item was added
new  |Value |	any	the new value, or null if an item was removed
url*	| string	| the page which called a method that triggered this change


* Note: the url property was originally called uri. Some browsers shipped with that
 property before the specification changed. For maximum compatibility, you should check whether the url property exists, and if not, check for the uri property instead.


## HTML5 STORAGE IN ACTION
 The most important part of this function is Data, Data is stored as strings. If you are storing something other than a string, you’ll need to coerce it yourself when you retrieve it. For example, the flag for whether there is a game in progress (gGameInProgress) is a Boolean. In the saveGameState() function, we just stored it and didn’t worry about the datatype:

## BEYOND NAMED KEY-VALUE PAIRS: COMPETING VISIONS
A new API has been standardized and implemented across all major browsers, platforms, and devices. As a web developer, that’s just not something you see every day, is it? But there is more to life than “5 megabytes of named key/value pairs,” and the future of persistent local storage is… how shall I put it… well, there are competing visions.

 *actual working code in 4 browsers*

 ```
 openDatabase('documents', '1.0', 'Local document storage', 5*1024*1024, function (db) {
  db.changeVersion('', '1.0', function (t) {
    t.executeSql('CREATE TABLE docids (id, name)');
  }, error);
});
```


### WEB SQL DATABASE SUPPORT

IE	|FIREFOX |	SAFARI |	CHROME |	OPERA|	IPHONE |	ANDROID
-----|--------|----------|----------|---------|----------|------------
 \-  |	-   | 	4.0+	| 4.0+   | 	10.5+	 |3.0+  |	2.0+

## the Indexed Database API, formerly known as “WebSimpleDB,” now affectionately known as “IndexedDB.”

The Indexed Database API exposes what’s called an object store. An object store shares many concepts with a SQL database. There are “databases” with “records,” and each record has a set number of “fields.” Each field has a specific datatype, which is defined when the database is created. You can select a subset of records, then enumerate them with a “cursor.” Changes to the object store are handled within “transactions.”

Read more about [HTML5 Storage ](https://html.spec.whatwg.org/multipage/webstorage.html) specification , [Web SQL Database ](https://dev.w3.org/html5/webdatabase/) ,[The Indexed Database API](https://w3c.github.io/IndexedDB/) .
