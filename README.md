http://c16e.com/1510161700/

stage=0オプションが使えなくなっていたので以下を参考に修正
http://qiita.com/suin/items/00f6dc9e910eaeb6476d

main.jsを書き換えてnpm run watchしようとしたら動かなかった。
```
react-like-button$ npm run watch

> react-like-button@0.0.0 watch /Users/kazuma_ns/develop/private/study/react-like-button
> rm -rf dist/*.js && webpack -w

Hash: 0231ab4c7cce0be07b92
Version: webpack 1.12.14
Time: 14536ms
    + 1 hidden modules

ERROR in ./src/main.js
Module build failed: SyntaxError: /Users/kazuma_ns/develop/private/study/react-like-button/src/main.js: Unexpected token (7:6)
   5 |   render() {
   6 |     return (
>  7 |       <span>いいねボタン予定地</span>
     |       ^
   8 |     );
   9 |   }
  10 | }
    at Parser.pp.raise (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:1375:13)
    at Parser.pp.unexpected (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:2813:8)
    at Parser.pp.parseExprAtom (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:747:12)
    at Parser.pp.parseExprSubscripts (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:502:19)
    at Parser.pp.parseMaybeUnary (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:482:19)
    at Parser.pp.parseExprOps (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:413:19)
    at Parser.pp.parseMaybeConditional (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:395:19)
    at Parser.pp.parseMaybeAssign (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:358:19)
    at Parser.pp.parseParenAndDistinguishExpression (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:820:26)
    at Parser.pp.parseExprAtom (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:706:19)
    at Parser.pp.parseExprSubscripts (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:502:19)
    at Parser.pp.parseMaybeUnary (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:482:19)
    at Parser.pp.parseExprOps (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:413:19)
    at Parser.pp.parseMaybeConditional (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:395:19)
    at Parser.pp.parseMaybeAssign (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:358:19)
    at Parser.pp.parseExpression (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:322:19)
    at Parser.pp.parseReturnStatement (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:2026:26)
    at Parser.pp.parseStatement (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:1814:19)
    at Parser.pp.parseBlockBody (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:2204:21)
    at Parser.pp.parseBlock (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:2185:8)
    at Parser.pp.parseFunctionBody (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:1123:22)
    at Parser.pp.parseMethod (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:1092:8)
    at Parser.pp.parseClassMethod (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:2491:8)
    at Parser.pp.parseClassBody (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:2452:10)
    at Parser.pp.parseClass (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:2335:8)
    at Parser.pp.parseStatement (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:1809:19)
    at Parser.pp.parseBlockBody (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:2204:21)
    at Parser.pp.parseTopLevel (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:1743:8)
    at Parser.parse (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:1346:17)
    at Object.parse (/Users/kazuma_ns/develop/private/study/react-like-button/node_modules/babel-core/node_modules/babylon/index.js:45:50)
```

記事の内容が古くて今のbabelでは読み込めない？

他の情報もあたって、動くように修正しよう。
とりあえず見つかった情報を以下に貼っておく。
http://minotaur.badwitch.io/react-webpack-boilerplate/