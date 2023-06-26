<template>
  <div>
    <h3 class="text-center p-4 text-white">DAFTAR NILAI SISWA KELAS XII</h3>
    <section
      class="d-flex flex-row border border-primary rounded-xl p-5 mt-2 mb-2 bg-dark text-white shadow-xl"
    >
      <div class="input-group mb-3">
        <div class="form-floating">
          <label for="floatingInputGroup1">Nomor Induk Siswa</label>
          <input
            v-model="nis"
            type="number"
            class="form-control"
            id="floatingInputGroup1"
            placeholder="Nomor Induk Siswa"
            
          />
        </div>
      </div>
      <div class="input-group mb-3">
        <div class="form-floating">
          <label for="floatingInputGroup1">Nama Siswa</label>
          <input
            v-model="nama"
            type="text"
            class="form-control"
            id="floatingInputGroup1"
            placeholder="Nama SIswa"
          />
        </div>
      </div>
      <div class="input-group mb-3">
        <div class="form-floating">
          <label for="floatingInputGroup1">Nilai Siswa</label>
          <input
            v-model="nilai"
            type="number"
            class="form-control"
            id="floatingInputGroup1"
            placeholder="Nilai Siswa"
          />
        </div>
      </div>
      <button
        type="button"
        class="btn btn-success btn-xs btn-rounded"
        @click="
          $emit('tambahData', { nis, nama, nilai });
          hapusForm();
        "
      >
        Tambah
      </button>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nis: "",
      nama: "",
      nilai: "",
    };
  },
  methods: {
    hapusForm: function () {
      (this.nis = ""), (this.nama = ""), (this.nilai = "");
    },
  },
};
</script>

<style>
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
