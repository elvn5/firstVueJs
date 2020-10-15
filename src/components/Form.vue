<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Номер телефона"
        label-for="input-1"
        description="Ваши личные данные не будут переданы третьим лицам"
      >
        <b-form-input
          id="input-1"
          type="number"
          v-model="form.number"
          required
          placeholder="+996 700 200 100"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="Ваше имя" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.name"
          required
          placeholder="Аскар"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-3" label="Фамилия" label-for="input-3">
        <b-form-input
          id="input-3"
          v-model="form.surname"
          required
          placeholder="Закиров"
        ></b-form-input>
      </b-form-group>

      <b-button type="submit" variant="primary">Оставить заявку</b-button>
    </b-form>
  </div>
</template>

<script>
import axios from 'axios';
const baseURL = "http://localhost:3000/orders"
  export default {
    data() {
      return {
        form: {
          number: '',
          name: '',
          surname: ''
        },
        show: true
      }
    },
    methods: {

    async  onSubmit(evt) {
        evt.preventDefault()
        this.$swal('Ваша заявка принята в обработку');
        const res = await axios.post(baseURL, this.form)
      }
    }
  }
</script>
