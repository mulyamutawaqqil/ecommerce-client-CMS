<template>
  <div class="row" style="margin-top:10%">
    <div class="col-md-4"></div>
    <div class="col-md-4">
      <main class="form text-center">
      <form  v-on:submit.prevent='addProduct'>
        <h1 class="h3 mb-3 fw-normal">Add product</h1>
        <div class="form-group">
          <label for="category">Select the category...</label>
          <select class="form-control" id="category" v-model="category">
            <option value="Makeup">Makeup</option>
            <option value="Skincare">Skincare</option>
            <option value="Haircare">Haircare</option>
          </select>
        </div>
        <input type="text" id="name" class="form-control" placeholder="Product name" required autofocus v-model="name"><br>
        <input type="text" id="image_url" class="form-control" placeholder="Image Url" required v-model="imageUrl"><br>
        <input type="text" id="price" class="form-control" placeholder="Price" required v-model="price"><br>
        <input type="text" id="stock" class="form-control" placeholder="Stock" required v-model="stock"><br>
        <button class="w-100 btn btn-lg btn-success" type="submit">Add product</button>
      </form>
    </main>
    </div>
    <div class="col-md-4"></div>
  </div>
</template>

<script>
export default {
  name: 'AddProduct',
  data () {
    return {
      name: '',
      imageUrl: '',
      category: 'select the category',
      price: '',
      stock: ''
    }
  },
  methods: {
    addProduct () {
      const { name, imageUrl, category, price, stock } = this
      this.$store.dispatch('addProduct', { name, imageUrl, category, price, stock })
    }
  }

}
</script>

<style>

</style>
