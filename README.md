# tiptap-extension-bullet-list

<h3 align="center">
    Tiptap bullet list extension with custom list-style-type support.
</h3>

<br/>

<p align="center">
  <a href="https://www.npmjs.com/package/tiptap-extension-bullet-list">
    <img
     alt="NPM URL"
     src="https://img.shields.io/badge/npm-tiptapExtensionBulletList?logo=npm">
  </a>
  <img
     alt="version"
     src="https://img.shields.io/badge/version-1.0.0-blue">
</p>

<br>

---

## Install

```shell
npm install tiptap-extension-bullet-list -S
```

## Usage

```js
  const listType = e.target.dataset.listType; // circle disc square
  let chain = editor.chain().focus();
  // 开启列表类型
  if (!editor.isActive('bulletList')) {
    chain.toggleBulletList().updateAttributes('bulletList', { listStyleType });
  }
  // 切换列表类型
  else if (editor.getAttributes('bulletList').listStyleType !== listStyleType) {
    chain.updateAttributes('bulletList', { listStyleType });
  }
  // 关闭列表类型
  else {
    chain.toggleBulletList();
  }
```

## Options

Add `listStyleType` option, other options are same as `@tiptap/extension-bullet-list`

```js
import BulletList from "tiptap-extension-bullet-list";

const editor = new Editor({
  element: document.querySelector(".editor"),
  extensions: [
    StarterKit,
    BulletList.configure({
      listStyleType: 'disc', // default disc 
      HTMLAttributes: { class: "list-paddingleft-1" }
    }),
  ],
});
```

## Relations

**@tiptap/extension-bullet-list:** https://github.com/ueberdosis/tiptap/tree/develop/packages/extension-bullet-list

**tiptap-appmsg-editor:** https://github.com/KID-1912/tiptap-appmsg-editor