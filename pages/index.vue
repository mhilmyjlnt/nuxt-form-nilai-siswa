<template>
  <div class="d-flex flex-column bg-secondary min-vh-100">
    <Form @tambahData="tambahData" />
    <DataSiswa :data="siswaData" @hapusData="hapusData" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      siswaData: [],
    };
  },
  methods: {
    tambahData(data) {
      if(!data.nis || !data.nama || !data.length <= 0){
        alert("tebisa euy")
      } else{
        data = { ...data, id: Date.now() };
          this.siswaData.push(data);

      }
    },
    hapusData(id) {
      this.siswaData = this.siswaData.filter((items) => items.id !== id);
    },
  },
};
</script>
