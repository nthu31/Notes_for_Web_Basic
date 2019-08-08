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
    * Call Stack、Web Apis、Callback Stack、Event Loop的概念在chrome中的互動關係 (https://www.youtube.com/embed/8aGhZQkoFbQ), Example: setTimeOut() => Asynchronous
    * Outer Environment、Scope Chain的概念
    * Run in a single thread (bad for synchronous behavior)
    * 原型鍊prototype(可以達成共用function、類似繼承)，雖然ES6有class關鍵字，但事實上背後還是透過prototype來運作
    * Example: Array.prototype.any = function() {......}
    * function只是物件的一個特例

## ES6
    * 特性: default params、template literal、arrow function、Promise、let、const、class、模組module、map
    * Closure的概念
    * .call .apply的不同(call為明確指定this時、apply為明確指定this且函數沒有限定參數數量時)
    * bind (明確指定this時)
    * reduce的使用(不用每次都call外部的variable做累加)，code較乾淨
    * 使用eslint檢查code style，保證code的一致性

## Node.js
    * Node.js缺點：型態難以判斷、結構性不足、套件空間佔一大半、原始作者疏離
    * 如何在開發時將Node.js的runtime映射到外網 (連接到localhost:<port>)，而不需要雲端平台 => 使用ngrok or localtunnel
    * Node.js之父：Ryan Dahl
    * 面試問題: https://github.com/jimuyouyou/node-interview-questions
    * Session的使用: express.session package

## Docker
	* Volume的使用時機 (若不用volume，對filesystem的修改是local to container)

## SQL
    * 基本 FULL TUTORIAL: https://www.youtube.com/watch?v=qw--VYLpxG4
        create table、insert、select、update、delete
        Aggregation function不能放在where後面，因為where是為了select出哪些row需要被aggregation function compute
        GROUP BY、HAVING、LIKE
        注意WHERE(before calculation)和HAVING(after calculation)的差別（where不能包含aggregation function，having則包含）
    * 進階
        CREATE VIEW
        Foreign Keys
        Transaction(BEGIN; COMMIT; ROLLBACK; SAVEPOINT; ROLLBACK TO;)
        window function、over
        INHERITS 繼承
        ONLY(不對繼承的table做選取)
        Store Procedure 預存程序
        indexing (一般來說是B-Tree)
        Mockaroo: data generator

## NoSQL
    * Not Only SQL: example, MongoDB
    * 有類似table的結構，但不需預先定義schema，每一筆的欄位和數量可以不一樣
    * 譬如Mongo DB是No-relational、NoSQL、document based的database
    * 介紹: http://garyliutw.blogspot.com/2014/05/mongodb-nosql.html

## AWS
	* RDS (資料庫) 、S3 (CDN)
    * iT邦幫忙 AWS介紹 : https://ithelp.ithome.com.tw/articles/10192073
    * eb init會自動偵測你有沒有使用Dockerfile，自動幫你建立docker
    * eb 是和git整合的，要deploy之前要先做commit的動作 => commit -> deploy
    * 使用 express static -> cache control 讓browser或proxy cache static file
    * HTTPS SSL使用 (吳尚鴻ss-08 ch11 59:13) (Option)
    * SQS for Worker Environment
    * load balance

## Git
    * git flow的使用情境: master、develop、feature、hotfix、release 五大branches
    * 介紹 https://backlog.com/git-tutorial/tw/stepup/stepup1_4.html
    * 模擬 https://git-school.github.io/visualizing-git/
    * add / commit
    * push / pull
	* branch
	* merge
	* rebase

## CI/CD
    * CI工具Jenkins: 自動化建構、測試、部署等持續整合

## 知識
    * Session、Cookie的介紹與使用場景
    * 最大利潤問題(基本)
    * DevOps (開發與維護間的tradeoff)
    * 使用Redis的好處(key value pair)，Redis使用記憶體儲存，資料庫用硬碟儲存
    * 使用Redis實例: 短網址服務、統計系統、即時排名系統
    * SPA (single page application)例如：react router的功能
    * IIFE的作用 (主要用於隔離作用域，即執行function而不影響外界)
    * new 的背後發生什麼？
    * npm 的好處？
    * 什麼是nginx(HTTP和反向代理伺服器)，和Apache有什麼不同，Node.js呢? (三者的區別是什麼？)
    * SSL (Secure Sockets Layer，傳輸層安全性協定)
    * 網頁編碼:
        兩類:ANSI、Unicode
        ANSI: big5、dec8
        Unicode: utf-8
    * CAP定理: 一個分散式系統不可能同時滿足Consistency、Availability、Partition
    * ACID: 指資料庫管理系統（DBMS）在寫入或更新資料的過程中，為保證事務（transaction）是正確可靠的所需具備的特性
    * 物件導向Open-Closed Principle(開放-封閉原則): 程式容易擴充新功能，但是不用修改原始碼
    * Regular Expression: https://larry850806.github.io/2016/06/23/regex/
    * require vs include

## 設計模式
    * Simple Factory Pattern(簡單工廠模式)
    * Factory Method Pattern(工廠方法模式): https://blog.amowu.com/2009/08/factory-pattern.html 以增加code取代改code，在開發時比較能夠做到分工，而不是很多人改同一區塊的code
    * Abstract Factory Pattern: 跟上面方法差不多，只是加入了第二組產品
    * Observe Pattern(觀察者模式): https://dotblogs.com.tw/joysdw12/2013/03/13/96531

## Design Pattern

## 細節
	* react在render時只能包一個，所以最好用<div></div>包起來
	* 利用chrome的react dev tool做debug(debugger; in react)
	* static propTypes => props checking
	* In webpack.config 加上 devtool: 'cheap-source-map'來map bundle和原始code，debug會更容易知道是哪行出錯

## 基本OS
    * Program、Process、Thread的區別
    * Process程式執行三大區塊：global、stack、heap
    * IPC(inter-process communication)
    * Pipe、signal、socket、stream
    * stack memory(可預期生命週期) and heap memory(動態配置空間)
    * 排程: FCFS、SJF、RR、HRRN、Priority、Multi-level queue
    * Deadlock: mutual exclusion、hold and wait、no preemption、circular wait
    * resource-allocation wait
    * 處理deadlock: Prevention、Avoidance(avoidance、Banker's algorithm)、Detection、Ignore
    * interrupt, hardware interrupt = signal, software interrupt = trap
    * Main memory: CPU can access directly
    * Dual mode, Priviledge instruction, Hardware Protection
    * Communication Model: Message Passing、Share Memory
    * System Call vs. API (API是system call的封裝，system call是直接關聯到OS的)
    * win32 API、POSIX API、JAVA API
    * Treads have the same code section、global、os resource, but have their own stack、register set、program counter
    * Process Control Table (PCB)
    * Context Switch (overhead, Time-Sharing)
    * Process Scheduling Queue
    * CPU scheduling、Job scheduling、Job swapping
    * Tree of Processes
    * Interprocess Communication (IPC): share memory(較快，不用copy), message passing(較慢)
    * Socket、RPC
    * producer-consumer problem
    * Stub
    * Multithreads、Challenge in Multicore Programming
    * User threads: POSIX Pthreads、Win32 threads、Java threads from thread library
    * Kernel threads
    * Process Scheduling(when?)
    * Preemptive vs Non-Preemptive
    * Scheduling Criteria
    * FCFS、SJF、RR、Priority、multi-queue
    * Approximate SJF(predict the next CPU burst)
    * process affinity to processor
    * NUMA vs UMA
    * Process synchronization
    * Race Condition
    * critical section problem: multiple processes and share data
    * mutual exclusion、progress、bounded waiting
    * software support: mutex、semaphore、bakery algorithm
    * hardware support: TestAndSet()、Swap()
    * condition variable

## 網路
    * 3-way handshake / 4-way handshake
    * TCP/IP: 主要解決如何傳輸數據
    * HTTP: 主要解決如何包裝數據，每次請求都發起連結，較耗時間和資源，單向通道
    * Websocket: 也是一種協議，地位相當於HTTP，但效率更高為全雙工通道，常用於real time data transfer
    * Socket: 不是協議，只是TCP/IP的接口
    * https://twgame.wordpress.com/2015/02/03/tcpiphttpsocketudp/
    * https://blog.csdn.net/SL_ideas/article/details/73648378
    * 什麼是HTTP/2
    * 什麼是google protobuf
    * 什麼是telnet/ssh
## Python
    * 執行流程: https://medium.com/citycoddee/python%E9%80%B2%E9%9A%8E%E6%8A%80%E5%B7%A7-5-python-%E5%88%B0%E5%BA%95%E6%80%8E%E9%BA%BC%E8%A2%AB%E5%9F%B7%E8%A1%8C-%E7%9B%B4%E8%AD%AF-%E7%B7%A8%E8%AD%AF-%E5%AD%97%E7%AF%80%E7%A2%BC-%E8%99%9B%E6%93%AC%E6%A9%9F%E7%9C%8B%E4%B8%8D%E6%87%82-553182101653
    * yield、call stack、yield from: https://blog.blackwhite.tw/2013/05/python-yield-generator.html
    * iterator、iterable
    * generator
    * python2 與 python3的差別
    * 原始碼 -> 位元碼 -> 機械碼
    * 抽象滲漏
    * enumerate、zip、map、filter、args、kwargs
    * list, tuple, dictionary, set 底層實現: https://blog.csdn.net/siyue0211/article/details/80560783
    * hash解決衝突的辦法: 開放尋址(Python)、link-list(Java)
    * lambda的使用
    * parameters passing by value or reference
    * 閉包

##其他面試問題
    * https://www.twblogs.net/a/5c650a70bd9eee06ee22c866
    * node.js後端： https://www.ptt.cc/bbs/Soft_Job/M.1523009377.A.50D.html
    * 經典DP問題: Climb stairs(固定某些步數，求幾種方法到達n階)
    * 後端面試題: https://www.ptt.cc/bbs/Soft_Job/M.1551251447.A.362.html
    * https://medium.com/@hothero/2017-%E5%BE%8C%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%AB%E9%9D%A2%E8%A9%A6%E4%BB%A5%E5%8F%8A%E6%BA%96%E5%82%99%E7%B6%93%E9%A9%97-5e6083ef350
    * 後端工程師面試以及準備經驗: https://medium.com/@hothero/2017-%E5%BE%8C%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%AB%E9%9D%A2%E8%A9%A6%E4%BB%A5%E5%8F%8A%E6%BA%96%E5%82%99%E7%B6%93%E9%A9%97-5e6083ef350
    * 成大學生面試: https://hackmd.io/@garychen/ByvJsnBfl?type=view

## Leetcode
    * DP: Sherlock and cost、Climb stairs、Coin change

## 求職
    * Backend TW
    * Yourator (較多新創)
    * CakeResume
    * GitHub後端、全端
    * 104、1111
