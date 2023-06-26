<template>
  <div>
    <section
      class="d-flex flex-column border border-primary rounded-xl p-5 mt-2 mb-2 bg-dark text-white shadow-xl"
    >
      <h2 class="text-center">Nilai rata-rata : {{ nilaiAvg }}</h2>
      <table class="table text-white">
        <thead class="">
          <tr>
            <th scope="col">ID</th>
            <th scope="col">Nomor Induk Siswa</th>
            <th scope="col">Nama Siswa</th>
            <th scope="col">Nilai Siswa</th>
            <th scope="col">Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="items of data" :key="items.id">
            <td>{{ items.id }}</td>
            <td>{{ items.nis }}</td>
            <td>{{ items.nama }}</td>
            <td>{{ items.nilai }}</td>
            <td>
              <button
                @click="$emit('hapusData', items.id)"
                class="btn btn-danger"
              >
              Hapus
            </button>
            </td>
          </tr>
        </tbody>
      </table>
    </section>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Array,
      required: true,
    }
  },
  computed: {
    nilaiAvg(){
      if (this.data.length > 0) {
        const sum = this.data.reduce((sum, items) => sum + items.nilai, 0);
        return sum / this.data.length;
      } else {
        return 0;
      }
    }
  }
}
</script>

<style></style>
