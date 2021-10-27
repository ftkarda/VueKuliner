<template>
  <div class="row mt-4">
    <div class="col">
      <div class="d-flex h-100">
        <div class="justify-content-center align-self-center">
          <h2>
            <strong>Delicious Food Menu, </strong> <br />
            in Your Gadget
          </h2>
          <p>Ayo Segera Pilih dan Pesan Makanan Favorit Anda</p>
          <router-link class="btn btn-lg btn-success" to="/foods">
            <b-icon-arrow-right></b-icon-arrow-right> Pesan
          </router-link>
        </div>
      </div>
    </div>
    <div class="col">
      <img src="../assets/hero.png" width="100%" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero",
};
</script>

<style>
.btn-success {
  background-color: #4eb883;
}
</style>