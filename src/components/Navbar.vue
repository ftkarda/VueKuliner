<template>
  <div>
    <b-navbar id="nav" toggleable="lg" type="light">
      <div class="container">
        <b-navbar-brand>
          <router-link class="navbar-brand" to="/"
            >Kulineran</router-link
          ></b-navbar-brand
        >

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <router-link class="nav-link" to="/">Home</router-link>
            <router-link class="nav-link" to="/foods">Foods</router-link>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <li class="navbar-nav ml-auto">
              <router-link class="nav-link" to="/keranjang"
                >Keranjang <b-icon-bag></b-icon-bag>
                <span class="badge badge-success ml-2">
                  {{
                    updateKeranjang
                      ? updateKeranjang.length
                      : jumlah_pesanans.length
                  }}
                </span>
              </router-link>
            </li>
          </b-navbar-nav>
        </b-collapse>
      </div>
    </b-navbar>
  </div>

  <!-- <nav  class="navbar navbar-expand-lg navbar-light">
    <div class="container">
      <router-link class="navbar-brand" to="/">Kulineran</router-link>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <router-link class="nav-link" to="/">Home</router-link>
          <router-link class="nav-link" to="/foods">Foods</router-link>
        </ul>
        <ul class="navbar-nav ml-auto">
          <router-link class="nav-link" to="/keranjang"
            >Keranjang <b-icon-bag></b-icon-bag>
            <span class="badge badge-success ml-2">
              {{ updateKeranjang ? updateKeranjang.length : jumlah_pesanans.length }}
            </span>
          </router-link>
        </ul>
      </div>
    </div>
  </nav> -->
</template>

<script>
import axios from "axios";

export default {
  name: "Navbar",
  data() {
    return {
      jumlah_pesanans: [],
    };
  },
  props: ["updateKeranjang"],
  methods: {
    setJumlah(data) {
      this.jumlah_pesanans = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/keranjangs")
      .then((response) => this.setJumlah(response.data))
      .catch((error) => console.log("Gagal : ", error));
  },
};
</script>

<style></style>
