node-diary
===

[![Build Status](https://travis-ci.org/tatsy/node-diary.svg?branch=master)](https://travis-ci.org/tatsy/node-diary)
[![Coverage Status](https://coveralls.io/repos/tatsy/node-diary/badge.svg?branch=master)](https://coveralls.io/r/tatsy/node-diary?branch=master)
[![Dependency Status](https://david-dm.org/tatsy/node-diary.svg)](https://david-dm.org/tatsy/node-diary)

> A simple diary tool using Node.js

## Install

The installation requires two steps.

__Step 1.__ In the application root, execute,

```bash
npm install
```

__Step 2.__ In the __node_modules__ directory,

```bash
git clone https://github.com/tatsy/marked.git
cd marked
git checkout imgsize
```
(I have sent pull request to the original marked authors, so please wait for more simple installtion.)

__Step 3.__ Enable Evernote clipping

Please get **developer token** from [https://www.evernote.com/api/DeveloperToken.action](https://www.evernote.com/api/DeveloperToken.action).

Rename ```config.template.json``` to ```config.json``` and paste your developer token in the file.

## Usage

1. Execute **start-diary.cmd** (Windows), or **start-diary.sh** (Linux and MacOS).
2. Open [http://localhost:3000]() with your brouser.

## Special Markdown

### Number-based media specification

After you upload media files (image or viode files), you can specify them with a notation like __%1__.

```markdown
![](%1)
```

is interpreted as

```html
<img src="your_image_01.jpg" />
```

### Support ```<video>``` tag

```markdown
$[](your_movie.mp4)
```

is interpreted as

```html
<video src="your_movie.mp4" controls></video>
```

In addition, you can upload source code file as well as media files. Specifying a source file with __%1__ will be replaced by the source code

### Parallel video play

You can play multiple videos by placing them into a blackquote block and use a special markdown '''[Play]'''.

For example, following code will provide a play button for two videos put into a table.

```markdown
>| A | B |
|:-:|:-:|
|$[](%1)|$[](%2)|
[Play]
```

## Acknowledgment

* I thank Michael Dolejs for publicly providing Evernote icon in [IconFinder](https://www.iconfinder.com/).
