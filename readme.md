## node+typescript+express环境搭建

### 1、首先创建一个项目（新建一个目录）

### 2、初始化package.json

```js
npm init -y
```
### 3、安装库

```js
npm install express ts-node typescript nodemon -g
npm install @types/express @types/node  -D
```
### 4、新建目录

### 5、生成tsconfig，此文件是用于typescript编译用的

### 6、修改tsconfig.json，修改如下图所示：

rootDir指定编译目录

### 7、然后修改package.json文件中的scripts，修改内容如下：

```js
"scripts": {
    "tsc": "tsc",
    "start": "node build/app.js",
    "dev": "nodemon app/app.ts",
    "build": "tsc -p .",
    "test": "echo \"Error: no test specified\" && exit 1"
}
```

8、在app目录中新建一个app.ts文件
```typescript
import express, { Application, Request, Response, NextFunction } from 'express'
const app:Application = express();
app.get('/', (req:Request, res:Response, next:NextFunction) => {
   res.send('Hello World!');
});
app.listen(7777, function(){
    console.log('Example app listening on port 7777!');
})
```

9、通过npm run dev运行

10、然后在浏览器中输入127.0.0.1:7777即可显示出Hello World!如下图所示”
