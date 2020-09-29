# How Typescript & Babel work together?
#typescript, #babel
#### Workflow
1. IDE watcher tất cả các thay đổi của file TypeScript (*.ts)
2. IDE gọi TypeeScript và convert sang ES6 Javascript
3. IDE watcher tất cả các file JavaScript và invoké Babel
4. Tất cả các file JavaScript sẽ được chuyển qua ES5 JavaScript

#### IDE CONFIGURATION 
- [[ide-babel-watcher]]: BABEL WATCHER
- [[ide-typescript-watcher]]: TYPESCRIPT WATCHER


http://codecounselor.org/technology/2016/03/21/typescript-and-es6.html