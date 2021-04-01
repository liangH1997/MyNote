## v-for 和 v-if 不能共用的解决方案
``` html
<template v-for="(item,index) in tableHeaderOptions">
    <el-table-column
      :label="item.label"
      :key="item.prop + index"
      :fixed="item.fixed"
      :prop="item.prop"
      v-if="item.show"
    >
    </el-table-column>
</template>
```
