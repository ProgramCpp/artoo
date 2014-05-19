---
layout: page
title: artoo.save
id: save
---

# {{ page.title }}

---

**artoo**'s save module enables you to download various things from JavaScript.

If your browser warns you about the webpage trying to download several items, just tell him it's gonna be ok and you should not be bothered again.

**Note**: every methods below can take the same parameters object as `artoo.save`. It's just that they are not documented each time.

---

* [artoo.save](#save)
* [artoo.saveJson](#json)
* [artoo.savePrettyJson](#pretty)
* [artoo.saveCsv](#csv)
* [artoo.saveHtml](#html)
* [artoo.savePageHtml](#page-html)
* [artoo.saveStore](#store)
* [artoo.saveInstructions](#instructions)

---

<h2 id="save">artoo.save</h2>
Download data according to given parameters. This function should only be used if the next functions cannot satisfy your needs.

```js
artoo.save(data, [params]);
```

*Arguments*

* **data**   *string* : data to download.
* **params** *?object* : an object that may contain the following properties:
  * **mime**     *?string* : mime type of the file to download. Note that **artoo** provide some shortcuts for popular types such as `json`, `csv` `text` and `html`.
  * **encoding** *?string* : encoding of the file to download.
  * **filename** *?string* : name of the file to download.

---

<h2 id="json">artoo.saveJson</h2>
Dowload a JavaScript variable or a JSON string as a JSON file.

```js
artoo.saveJson(data, [params]);
```

*Additional parameters*

* **pretty** *?boolean* [`false`] : should the ouput JSON file be pretty-printed?
* **indent** *?integer* [`2`] : By how many spaces should we indent the JSON file?

*Example*

```js
artoo.saveJson({hello: world}, {filename: 'hello-world.json'});
```

---

<h2 id="pretty">artoo.savePrettyJson</h2>
Dowload a JavaScript variable or a JSON string as a pretty-printed JSON file.

```js
artoo.savePrettyJson(data, [params]);
```

This is the same as doing

```js
artoo.saveJson(data, {pretty: true});
```

---

<h2 id="csv">artoo.saveCsv</h2>
Download an array of array or an array of objects or a string as a CSV file.

```js
artoo.saveCsv(data, [params]);
```

*Additional parameters*

* **delimiter** *?string* [`,`] : the field delimiter.
* **escape**    *?string* [`"`] : the escape character.

*Example*

```js
var persons =[
   {
     firstname: 'Caroline',
     lastname: 'Williams'
   },
   {
     filename: 'Steven',
     lastname: 'Douglas'
   }
];

artoo.saveCsv(persons);
```

For more precisions, refer to [artoo.helpers.toCSVString]({{ site.baseurl }}/helpers#to-csv-string) method.
