<template>
  <tr @click="selectitem(index)">
    <th scope="row">
      <input type="checkbox" name id v-model="item.isSelected" />
    </th>
    <td>{{ index + 1 }}</td>
    <td>{{ item.msg }}</td>
    <td>{{ item.endtime }}</td>
    <td>{{ item.completed }}</td>
    <td>
      <div class="btn-group mr-2" role="group" aria-label="First group">
        <button type="button" class="btn btn-success btn-sm" @click.stop.once="changeitem()">完成</button>
        <button type="button" class="btn btn-danger btn-sm" @click.stop="removeitem()">删除</button>
      </div>
    </td>
  </tr>
</template>
<script>
import Bus from "../bus.js";
export default {
  props: ["item", "index", "remove", "change", "select"],
  methods: {
    changeitem() {
      // this.change(this.index);
      Bus.$emit("changeitem", this.index);
    },
    removeitem() {
      // this.remove(this.index);
      Bus.$emit("removeitem", this.index);
    },
    selectitem() {
      // this.select(this.index);
      Bus.$emit("selectitem", this.index);
    }
  }
};
</script>