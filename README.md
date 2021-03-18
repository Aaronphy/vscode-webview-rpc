# Welcome to vscode-webview-prc 👋
![Version](https://img.shields.io/badge/version-0.0.1-blue.svg?cacheSeconds=2592000)
![Prerequisite](https://img.shields.io/badge/node-%3E%3D10-blue.svg)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#)

> a rpc lib for vscode webview extension development

## Prerequisites

- node >=10

## Install

```sh
yarn add vscode-webview-rpc
```

## Usage

> extension rpc
```js
import * as vscode from 'vscode';
import { ExtensionRPC } from 'vscode-webview-rpc';


const panel = vscode.window.createWebviewPanel(
			'EditPanel',
			'Blog Editing',
			column || vscode.ViewColumn.One,
			getWebviewOptions(extensionUri),
	);

const RPC = new ExtensionRPC(panel.webview);

RPC.on('log',(e)=>{
  console.log(e);
  return Promise.resolve();
});

```

> webview rpc

```js
import { WebviewRPC } from 'vscode-webview-rpc';

declare var acquireVsCodeApi: any;

let RPC:WebviewRPC;

(()=>{
   RPC = new WebRPC(window, vscode);
   setTimeout(()=>{
     RPC.emit('log',["hello world"]);
   },2000);
})();


```

## Author

👤 **aaronphy**

* Github: [@Aaronphy](https://github.com/Aaronphy)

## Show your support

Give a ⭐️ if this project helped you!


***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_