<template>
  <div>
      <Navbar />
      <div class="container">
          <div class="row justify-content-center mt-5">
              <div class="col text-center">
                     <img src="../assets/images/menunggu.png" width="300" alt="">
                  <h1><strong>Sukses</strong></h1>
                  <h2>Pesanan Anda Segera di Proses</h2>
               
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";

export default {
nama: "PesananSukses",
components: {
    Navbar,
},
};
</script>

<style>

</style>