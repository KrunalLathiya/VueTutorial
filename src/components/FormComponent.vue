<template>
  <div class="container">
  <form>
    <div class="field">
      <label class="label">Name</label>
      <div class="control">
        <input class="input col-is-4" type="text" v-model="item"/>
      </div>
  </div>
  <div class="field">
    <div class="control">
      <button class="button is-success" @click.prevent="addItems">Add</button>
    </div>
  </div>
</form>

<table v-if="items.length > 0" class="table is-striped">
  <tr>
    <th>Index</th>
    <th>Items</th>
    <th>Action</th>
  </tr>
  <tr v-for="(item, index) in items">
    <td>{{ index }}</td>
    <td>{{ item.message }}</td>
    <td>
      <button @click.prevent="deleteData(index)" class="button is-danger">Delete</button>
    </td>
  </tr>
</table>

</div>
</template>
<script>
export default {
  data: function(){
    return {
      item: '',
      items: []
    }
  },
  methods: {
    addItems(){
      this.items.push({message: document.querySelector('input').value});
      this.item = '';
    },
    deleteData(index){
      this.items.splice(index, 1);
    }
  }
}
</script>
