# Notes_for_Web_Basic
    Some questions and notes for the web development knowledges

## 基本
    * HTML / CSS / Javascript
    * React / Redux (前端框架)
    * Node.js (後端Javascript執行環境)
    * Axios (Package，為前端發送http request對AJAX的封裝)
    * Express (Node.js後端框架)

## 觀念
    * Component-base的前端開發
    * MVC (Model / View / Controller) 對應到 (Reducer / React / Redux的Action)
    * AJAX(Asynchronous Javascript And XML)

## Javascript
    * Chrome V8 Engine(2008年google的專案，為了加速Javascript在chrome執行的速度，written by C++)
    * Call Stack、Web Apis、Callback Stack、Event Loop的概念在chrome中的互動關係 (https://www.youtube.com/embed/8aGhZQkoFbQ)
    * Outer Environment、Scope Chain的概念
    * Run in a single thread (bad for synchronous behavior)
    * 原型鍊prototype(可以達成共用function、類似繼承)，雖然ES6有class關鍵字，但事實上背後還是透過prototype來運作

## ES6
    * Closure的概念
    * .call .apply的不同(call為明確指定this時、apply為明確指定this且函數沒有限定參數數量時)
    * bind (明確指定this時)
    * reduce的使用(不用每次都call外部的variable做累加)，code較乾淨

## Node.js
    * Node.js缺點：型態難以判斷、結構性不足、套件空間佔一大半、原始作者疏離
    * 如何在開發時將Node.js的runtime映射到外網 (連接到localhost:<port>)，而不需要雲端平台 => 使用ngrok or localtunnel
    * Node.js之父：Ryan Dahl

## Docker
	* Volume的使用時機 (若不用volume，對filesystem的修改是local to container)

## AWS
	* RDS (資料庫) 、S3 (CDN)

## Git
    * add / commit
    * push / pull
	* branch
	* merge
	* rebase

## 知識
    * DevOps (開發與維護間的tradeoff)
    * 使用Redis的好處(key value pair)，Redis使用記憶體儲存，資料庫用硬碟儲存
    * 使用Redis實例: 短網址服務
    * SPA (single page application)例如：react router的功能
    * IIFE的作用 (主要用於隔離作用域，即執行function而不影響外界)
    * new 的背後發生什麼？
    * npm 的好處？
    * 什麼是nginx(HTTP和反向代理伺服器)，和Apache有什麼不同，Node.js呢? (三者的區別是什麼？)
    * SSL (Secure Sockets Layer，傳輸層安全性協定)

## 細節
	* react在render時只能包一個，所以最好用<div></div>包起來
	* 利用chrome的react dev tool做debug(debugger; in react)
	* static propTypes => props checking
	* In webpack.config 加上 devtool: 'cheap-source-map'來map bundle和原始code，debug會更容易知道是哪行出錯

## 求職
    * Backend TW
    * Yourator (較多新創)
    * GitHub後端、全端
    * 104、1111
