# Wings Site

Official Wings WebSite repository. Based on Bootstrap/HTML5/CSS.

## Launch

This section shows how to launch a local version of the website using the `http-server` nodejs module.

Method requires `nodejs` and `npm` installed.

```sh
npm install -g http-server
cd <site-folder>
http-server
```

## Contribution 

Public contributions are welcome. Significant contributions will gain bounties as a reward.

Important note: we are using git flow to manage branches. Read more in [gitflow tutorial](http://danielkummer.github.io/git-flow-cheatsheet/) to follow our repository rules.

## Translations

This tutorial explains how to add a translation

### Fork Repository

First, fork this repository by clicking on the next button.

### Create new branch

Create a new branch in your version of repository and name it: `feature/<lang>` 

Replace `lang` with name of your language translation, for example `feature/<chinese>`.

### Create language files

First go to the `bundle` directory

Create a new file in this directory with following name:

```
Content_<langCode>.properties
```

Replace `<langCode>` with the relevant language code that you going to translate. For example:

* zh - Chinese.
* en_GB - Great Britain English.
* ru_RU - Russian.

You can find a full list of language codes on this [page](http://www.lingoes.net/en/translator/langcode.htm) (**Important**: use '_' instead of '-' in file name).

Open `bundle/languages.json` and add your translation language code to the list. For example:

```json
{
	"languages": [
		"en_GB",
		"ru_RU",
		"<add here>"
	]
}
```

Replace `<add here>` with the language code you are translating.

Open `bundle/json` folder and create same file for chat animation translation (see picture) or duplicate `bundle/json/chat_en_GB.json` and rename the newly created file:
Format of file name: `chat_<langCode>.json`. You need to replace <langCode> with **your** language code.

### Start translations (Site)

Open 'bundle/Content_en_GB.properties` file with the english translation and see format of this file:

```
<key>=<message>
```

The `key` is the id of the block of text that you are translating and the `message` is the text to translate.

For example, we will translate the Title block to Russian: 

The english `key` and `message`:

```
title=Wings - A decentralized platform to create, join and manage DAOs
```

Will look like this when translated in Russian:

```
title=Wings - Децентрализованная платформа для создания, участия и управления DAO
```

The `key` is `title` and it was not changed changed, but we did change the `message`.

Follow the same instruction for all the `keys` and `messages` in your language file.


### Start translations (Chat)

To translate the chat, open the newly created file `bundle/json/chat_<langCode>.json`. If you did not duplicate teh `bundle/json/chat_en_GB.json` when creating the chat translation file, copy the contents of `bundle/json/chat_en_GB.json` into the new `bundle/json/chat_<langCode>.json`.

This is a **json** file and contains **json** arrays of messages.

Example message array:

```json
{
	"author": "bot",
	"avatar": "images/bot.svg",
	"msg": "Hi! I am Wings DAO management bot. How may i be of service ?"
}
```

You need to translate `msg` field in each message array to make a correct translation of the chat.

### Make pull request of your translation

Commit your changes and make pull request from your branch to our repository.

## Copyrights

© 2016 ChainLab
