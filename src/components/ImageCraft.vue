<template>
  <div class="container d-flex flex-column justify-content-center align-items-center text-center" style="min-height: 100vh;">
      <h1 class="title-text text-image">Generate dummy images.</h1>
      <div>
        <div class="input-group mb-3">
          <span class="input-group-text" id="basic-addon1">Height(px)</span>
          <input v-model="height" type="text" class="form-control" placeholder="select PX" aria-label="Username" aria-describedby="basic-addon1">
        </div>
      </div>
      <div>
        <div class="input-group mb-3">
          <span class="input-group-text" id="basic-addon1">Width(px)</span>
          <input v-model="width" type="text" class="form-control" placeholder="select PX" aria-label="Username" aria-describedby="basic-addon1">
        </div>
      </div>
      <button @click="craftImage" class="btn btn-outline-danger">CREATE</button>
      <!-- 作成画像表示 -->
      <div v-if="imageUrl" class="imageDisplay">
        <img :src="imageUrl" :alt="'Dummy image of '+height+' x '+width">
      </div>
  </div>
</template>
<script>
export default {
  name: 'ImageCraft',
  props: {
    msg: String
  },
  data() {
    return {
      test: null,
      height: null,
      width: null,
      imageUrl: null,
      imageQuantity: null,
    }
  },
  methods: {
    craftImage() {
      if (this.height && this.width) {
        this.imageUrl = `https://via.placeholder.com/${this.width}x${this.height}`;
      }
    },
  }
}
</script>
