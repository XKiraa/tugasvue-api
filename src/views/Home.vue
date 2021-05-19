<template>
  <div class="home">
    <h1>Data Satpam Filkom</h1>
    <div class="container mt-3">
      <div class="row">
        <form class="row g-3" v-on:submit.prevent>
          <div class="col-6" align="left">
            <label for="inputNama" class="form-label mt-3" >Nama</label>
            <input type="text" class="form-control" id="inputNama" placeholder="Nama Lengkap" v-model="penjaga.nama">
          </div>
          <div class="col-6" align="left">
            <label for="inputId" class="form-label mt-3">Id Penjaga</label>
            <input type="text" class="form-control" id="inputId" placeholder="000" v-model="penjaga.id_penjaga">
          </div>
          <div class="col-6" align="left">
            <label for="inputJenis" class="form-label mt-3">Jenis Kelamin</label>
            <input type="text" class="form-control" id="inputJenis" placeholder="Jenis Kelamin" v-model="penjaga.jenis">
          </div>
          <div class="col-6" align="left">
            <label for="inputAlamat" class="form-label mt-3">Alamat</label>
            <input type="text" class="form-control" id="inputAlamat" placeholder="Alamat lengkap" v-model="penjaga.alamat">
          </div>
          <div class="col-6" align="left">
            <button type="submit" class="btn btn-primary mt-3" @click="kirim">Send</button>
          </div>
        </form>
        
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import axios from "axios";

export default {
  name: 'Home',
  components: {
    
  },
  data() {
      return {
        penjaga:{}
      }
  },
  methods:{
    kirim(){
      console.log(this.penjaga)
      axios
        .post("http://localhost:3000/penjaga", this.penjaga)
        .then(() => {
          console.log("success");
          this.$router.push({ path: "/about"})
        })
        .catch((err) => {
          console.log(err);
        })
    }
  },
  mounted(){

  }
}
</script>
