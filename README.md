# TypeScriptでJESTを使う
## 環境構築

1. 必要なnpm packageをinstallする

```
$ npm init -y
$ npm i jest
$ npm i ts-jest
$ npm i ts-node
$ npm i @types/jest
$ npm i @types/node
```
2. package.jsonを編集する
scriptsの中のtestの""の中の長い文字をtestに変更する

```json
{
  "name": "02",
  "version": "1.0.0",
  "description": "必要なnpm packageをinstallする",
  "main": "index.js",
  "scripts": {
    "test": "test"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "@types/jest": "^29.2.3",
    "@types/node": "^18.11.9",
    "jest": "^29.3.1",
    "ts-jest": "^29.0.3",
    "ts-node": "^10.9.1"
  }
}
```

3. 基本の設定ファイルを生成する

```
jest --init
```

```ts
module.exports = {
  roots: ['<rootDir>/src'],
  transform: {
      '^.+\\.tsx?$': 'ts-jest'
  },
  testRegex: '(/__test__/.*|(\\.|/)(test|spec))\\.[jt]sx?$',
  moduleFileExtensions: ['ts', 'tsx', 'js', 'jsx', 'json', 'node'],
  verbose: true
}
```
4. 最小限のテストコードを作成する

```
src
├── app
│   └── Utils.ts
└── test
    └── Utils.test.ts
```
