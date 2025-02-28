---
author: M.L De Veer
pubDatetime: 2026-02-24T06:00:00.000Z
title: Using JSON Files in C with CJSON 
slug: using-json-files-with-cjson
featured: false
draft: false
tags:
  - c
  - json
description: How to parse and update JSON files in C programming using CJSON.
---

There are quite a few articles out there on how to use CJSON, so it makes one wonder why another article on the same topic. Well... the problem with a lot of the articles in the top search results are usually the same. Literally most of them use the same examples and the problem with that is if those examples do not address the exact problem you have, it is the same across a lot of these articles. Using JSON in C was a first time for me and i was parsing with from a file, now you'd think most of the examples will address it from this point of view?, nope, they all used a json string. Now there's nothing wrong with that, the problem was the format of said json string. Afterall when you access the contents of the json file, you still get it's content as a character string. The problem stems from the structure of the string they are parsing. The json string example is usually in the form:

```c
char *json_string = "[items{"item": "socks","id": 1, "amount": 200, "price": 10}, {"item": "socks","id": 1, "amount": 200, "price": 10}]";
```

There's nothing wrong with this but most json files do not start with an array name, that is usually the file name. json files, especially ones with a lot of items are usually of the format:

```json
[{
		"machine":	"Larry",
		"id":	1,
		"ip":	"",
		"reserved":	true,
		"weeks":	1,
		"days":	0,
		"hours":	0
	}, {
		"machine":	"Testo",
		"id":	2,
		"ip":	"",
		"reserved":	false,
		"weeks":	0,
		"days":	0,
		"hours":	0
	}
]
```

and when you do get the file contents, it will be in the same format as it was in the file. So the examples these articles use will not work when you are trying to parse through the json string. Perhaps someone on having the same issue managed to figure it out... but i didn't and had to rely on chatgpt to find why no result was being printed out.

### Parsing the JSON file

To parse through a json file with cjson, you have to get the file contents. As shown below:

```c

```

to check if you have the file content you can simply just print out the string to make sure:

```c
```

now that we have our json string from the file, we can parse it. Using the previous example:

```c
```

### Updating the JSON file

now that we can parse through the json file contents using the json string, we should be able to update values and update the json file with said values. as shown bellow:

```c
```

