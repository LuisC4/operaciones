<template>
  <div class="container pt-5 pb-4">
    <h4 class="text-white mb-3">Operaciones aritméticas</h4>
    <b-form @submit.prevent>
      <div>
        <div class="form-group">
          <b-form-select
            v-model="selected"
            :options="options"
          ></b-form-select>
        </div>
          <div class="form-group">
            <div class="d-inline-block pr-2">
              <label
                class="form-label text-white"
                for="numeroUno"
              >Número Uno: </label>
            </div>
            <div class="d-inline-block">
              <input
                type="number"
                placeholder="0"
                id="numeroUno"
                class="form-control"
                v-model="numeroUno"
              >
            </div>
          </div>
      </div>
      <div>
          <div class="form-group">
            <div class="d-inline-block pr-2">
              <label
                class="form-label text-white"
                for="numeroDos"
              >Número Dos: </label>
            </div>
            <div class="d-inline-block">
              <input
                type="number"
                placeholder="0"
                id="numeroDos"
                class="form-control"
                v-model="numeroDos"
              >
            </div>
          </div>
      </div>
      <div>
        <button
          class="btn btn-info"
          @click="operacion"
        >Calcular</button>
        <h6 class="text-white mt-3">Resultado: {{ resultado }}</h6>
      </div>
    </b-form>

    <h4 class="text-white pt-5 mb-3">Grados Celcius a Fahrenheit</h4>

    <div>
    <b-form @submit.prevent>
      <div>
          <div class="form-group">
            <div class="d-inline-block pr-2">
              <label
                class="form-label text-white"
                for="numero"
              >Número: </label>
            </div>
            <div class="d-inline-block">
              <input
                type="number"
                placeholder="0"
                id="numero"
                class="form-control"
                v-model="numero"
              >
            </div>
          </div>
      </div>

      <div>
        <button
          class="btn btn-info"
          @click="grados"
        >Calcular Grados</button>
        <h6 class="text-white mt-5">Resultado: {{ resultadoGrados }}</h6>
      </div>
    </b-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selected: null,
      options: [
        { value: null, text: '-- Seleccione --' },
        { value: 'sum', text: 'Sumar' },
        { value: 'res', text: 'Restar' },
        { value: 'mul', text: 'Multiplicar' },
        { value: 'div', text: 'Dividir' }
      ],
      numeroUno: 0,
      numeroDos: 0,
      resultado: 0,
      resultadoGrados: 0,
      numero: 0
      }
  },
  methods: {
    operacion() {
      switch (this.selected) {
        case 'sum':
          this.resultado = parseFloat(this.numeroUno) + parseFloat(this.numeroDos);
          break
        case 'res':
          this.resultado = parseFloat(this.numeroUno) - parseFloat(this.numeroDos);
          break
        case 'mul':
          this.resultado = parseFloat(this.numeroUno) * parseFloat(this.numeroDos);
          break
        case 'div':
          this.resultado = parseFloat(this.numeroUno) / parseFloat(this.numeroDos);
          break
      }
    },
    grados() {
      this.resultadoGrados = ( this.numero * 9 / 5 ) + 32
    }
  },
}
</script>