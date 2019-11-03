# 简介

ElementUI's el-select combined with el-tree.

- Online examples [https://yujinpan.github.io/el-select-tree/](https://yujinpan.github.io/el-select-tree/);

## Usage

### Install

```
npm install --save el-select-tree
```

### Require element-ui

If your project does not use element-ui,
you need to introduce a separate element-ui package, like this:

```js
import 'el-select-tree/lib/element-ui';
```

### Global registration

```js
import Vue from 'vue';
import ElSelectTree from 'el-select-tree';

Vue.use(ElSelectTree);
```

### In-component registration

```js
import ElSelectTree from 'el-select-tree';

export default {
  components: {
    ElSelectTree
  }
};
```

### Complete example

````vue
<template>
  <el-select-tree
    :data="treeData"
    :disabled-values="disabledValues"
    v-model="value1"
  ></el-select-tree>
</template>

<script>
import ElSelectTree from 'el-select-tree';

export default {
  components: {
    ElSelectTree
  },
  data() {
    return {
      value: 2,
      treeData: [
        {
          value: 1,
          label: 'text1',
          children: [{ value: 5, label: 'text5' }, { value: 6, label: 'text6' }]
        },
        { value: 2, label: 'text2' },
        { value: 3, label: 'text3' },
        { value: 4, label: 'text5' }
      ],
      disabledValues: [3]
    };
  }
};</script
>```
````

## Component API

### Attributes

| name             | type       | description                                                                          |
| ---------------- | ---------- | ------------------------------------------------------------------------------------ |
| `value/v-model`  | `*/*[]`    | bound value, the type must be array if attribute's `multiple` is true                |
| `data`           | `object[]` | select options, is a tree data                                                       |
| `props`          | `object`   | tree data props, default: `{ value: 'value', label: 'label', children: 'children' }` |
| `multiple`       | `boolean`  | multiple selection, default: `false`                                                 |
| `width`          | `string`   | default: `240px`                                                                     |
| `disabled`       | `boolean`  | selection disabled, default: `false`                                                 |
| `disabledValues` | `*[]`      | options disabled                                                                     |

### Events

- `change(value)` options change, return changed value
