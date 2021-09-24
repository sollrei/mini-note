## ESlint
可以给文件添加`/* eslint-disable */`，或者对某块代码禁用警告
```javascript
/* eslint-disable */
alert(1);
/* eslint-enable */

/* eslint-disable no-alert, no-console */
alert(1);
console.log(2);
/* eslint-enable no-alert, no-console */

// 对某一行代码
alert(1); // eslint-disable-line

// eslint-disable-next-line no-alert
alert(1);
```
参考配置[Configuring ESLint - ESLint - Pluggable JavaScript linter](https://eslint.org/docs/user-guide/configuring#disabling-rules-with-inline-comments)

## Scss Lint
添加`scss-lint:disable`和需要禁用的lint规则，结束地方需要添加`scss-lint:enable`；使用`scss-lint:disable all`可以忽视所有规则
```scss
// scss-lint:disable ImportantRule, StringQuotes
p {
  text-decoration: none !important;  // No lint reported
  content: "hello"; // No lint reported
}
// scss-lint:enable ImportantRule, StringQuotes
div {
  text-decoration: none !important; // Lint reported
  content: "hello"; // Lint reported
}
```
或者添加在某个代码块内
```scss
p {
  // scss-lint:disable BorderZero
  border: none; // No lint reported
}

a {
  border: none; // Lint reported
}
```
对所有规则
```scss
// scss-lint:disable all
p {
  border: none; // No lint reported
}
// scss-lint:enable all

a {
  border: none; // Lint reported
}
```
参考[GitHub - brigade/scss-lint: Configurable tool for writing clean and consistent SCSS](https://github.com/brigade/scss-lint/#disabling-linters-via-source)
