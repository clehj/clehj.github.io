---
title: HelloWorld
date: 2024-04-16
tags: [HelloWorld, vue, vitepress]
pinned: false
head:
  - - meta
    - name: description
      content: vitepress-theme-bluearchive HelloWorld
  - - meta
    - name: keywords
      content: vitepress theme bluearchive HelloWorld
---

只是一个 HelloWorld

---

# Markdown Extension Examples

This page demonstrates some of the built-in markdown extensions provided by VitePress.

## Syntax Highlighting

VitePress provides Syntax Highlighting powered by [Shiki](https://github.com/shikijs/shiki), with additional features like line-highlighting:

**Input**

````md
```js{4}
export default {
  data () {
    return {
      msg: 'Highlighted!'
    }
  }
}
```
````

**Output**

```js{4}
export default {
  data () {
    return {
      msg: 'Highlighted!'
    }
  }
}
```

## Custom Containers

**Input**

```md
::: info 信息
这是一个信息框。
:::

::: tip
这是一个提示。
:::

::: warning
这是一个警告。
:::

::: danger STOP
这是一个危险的警告。
:::

::: details 点我查看
这是一个 详细 块。
:::

::: details 点我查看代码
//```js
//console.log('Hello, VitePress!')
//```
:::
```

**Output**

::: info 信息
这是一个信息框。
:::

::: tip
这是一个提示。
:::

::: warning
这是一个警告。
:::

::: danger STOP
这是一个危险的警告。
:::

::: details 点我查看
这是一个 详细 块。
:::

::: details 点我查看代码
```js
console.log('Hello, VitePress!')
```
:::

## More

Check out the documentation for the [full list of markdown extensions](https://vitepress.dev/guide/markdown).
