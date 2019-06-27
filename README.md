# direct-mail

[![Build Status](https://travis-ci.com/FEMessage/direct-mail.svg?branch=master)](https://travis-ci.com/FEMessage/direct-mail)
[![NPM Download](https://img.shields.io/npm/dm/@femessage/direct-mail.svg)](https://www.npmjs.com/package/@femessage/direct-mail)
[![NPM Version](https://img.shields.io/npm/v/@femessage/direct-mail.svg)](https://www.npmjs.com/package/@femessage/direct-mail)
[![NPM License](https://img.shields.io/npm/l/@femessage/direct-mail.svg)](https://github.com/FEMessage/direct-mail/blob/master/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/FEMessage/direct-mail/pulls)
[![Automated Release Notes by gren](https://img.shields.io/badge/%F0%9F%A4%96-release%20notes-00B2EE.svg)](https://github-tools.github.io/github-release-notes/)

阿里云 邮件推送 (DirectMail) Node.js SDK(兼容浏览器端)

## Table of Contents

* [Feature](#feature)
* [Install](#install)
* [Example](#example)
* [Reference](#reference)
* [Contributors](#contributors)
* [License](#license)

## Feature

* 兼容 Node.js/浏览器端
* Promise 风格
* 支持以下 API
  * SingleSendMail 单一发信接口，支持发送触发和其他单个邮件
  * BatchSendMail 批量发信接口，支持通过调用模板的方式发送批量邮件

[⬆ Back to Top](#table-of-contents)

## Install

```sh
yarn add @femessage/direct-mail
```

[⬆ Back to Top](#table-of-contents)

## Example

### 发送单个邮件

```js
const directMail = require('@femessage/direct-mail')

const singleConfig = {
  AccountName: 'yourmail@mail.com',
  FromAlias: '化名',
  ToAddress: 'toaddress@mail.com',
  Subject: '标题',
  HtmlBody: '<html>内容</html>',
  AccessKeySecret: '',
  AccessKeyId: ''
}

directMail
  .SingleSendMail(singleConfig)
  .then(resp => {})
  .catch(err => {})
```

### 批量发送邮件

```js
const directMail = require('@femessage/direct-mail')

const batchConfig = {
  AccountName: 'yourmail@mail.com',
  ReceiversName: 'defaultReceivers',
  TemplateName: 'offer',
  AccessKeySecret: '',
  AccessKeyId: ''
}

directMail
  .BatchSendMail(batchConfig)
  .then(resp => {})
  .catch(err => {})
```

### dotenv

AccessKeyId、AccessKeySecret 也可以通过环境来设置。

推荐使用[dotenv](https://www.npmjs.com/package/dotenv)

```sh
#.env
ACCESS_KEY_ID=
ACCESS_KEY_SECRET=
```

则可以在调用时，不用传 AccessKeyId、AccessKeySecret

```js
const config = {
  AccountName: 'yourmail@mail.com',
  FromAlias: '化名',
  ToAddress: 'toaddress@mail.com',
  Subject: '标题',
  HtmlBody: '<html>内容</html>'
}

directMail
  .SingleSendMail(config)
  .then(resp => {})
  .catch(err => {})
```

[⬆ Back to Top](#table-of-contents)

## Reference

* 更多参数说明，请看[aliyun official docs](https://help.aliyun.com/document_detail/29444.html?spm=a2c4g.11186623.6.597.22653016eJ4hhp)
* 产品相关使用手册，请看[FAQ](docs/faq.md)

[⬆ Back to Top](#table-of-contents)

## Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->

<!-- prettier-ignore -->
<table><tr><td align="center"><a href="https://github.com/levy9527/blog"><img src="https://avatars3.githubusercontent.com/u/9384365?v=4" width="100px;" alt="levy"/><br /><sub><b>levy</b></sub></a><br /><a href="https://github.com/FEMessage/direct-mail/commits?author=levy9527" title="Code">💻</a> <a href="https://github.com/FEMessage/direct-mail/commits?author=levy9527" title="Tests">⚠️</a> <a href="https://github.com/FEMessage/direct-mail/commits?author=levy9527" title="Documentation">📖</a></td><td align="center"><a href="https://github.com/donhac"><img src="https://avatars0.githubusercontent.com/u/9813324?v=4" width="100px;" alt="donhac"/><br /><sub><b>donhac</b></sub></a><br /><a href="https://github.com/FEMessage/direct-mail/commits?author=donhac" title="Code">💻</a> <a href="https://github.com/FEMessage/direct-mail/commits?author=donhac" title="Documentation">📖</a> <a href="#infra-donhac" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a></td></tr></table>

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

[⬆ Back to Top](#table-of-contents)

## License

[MIT](./LICENSE)

[⬆ Back to Top](#table-of-contents)

## Inspiration

thanks to [Mttylzq](https://github.com/Mttylzq/ali-email)