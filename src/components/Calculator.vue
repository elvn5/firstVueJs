<template>
  <b-container class="calculator">
    <form>
      <div class="row mb-3">
        <div class="form-group col-md-6 col-sm-6">
          <p class="badge badge-warning">Вес (кг)</p>
          <input
            type="text"
            name="date"
            class="form-control"
            id="weight"
            required=""
            placeholder="1500"
            v-model="form.weight"
          />
        </div>
        <div class="form-group col-md-6 col-sm-6">
          <p class="badge badge-warning">Объем (куб²)</p>
          <input
            type="text"
            name="adress"
            id="vol"
            class="form-control"
            placeholder="2"
            required=""
            v-model="form.size"
          />
        </div>
      </div>
      <div
        class="custom-control custom-checkbox row d-flex justify-content-center mb-3"
      >
        <div class="col-md-3" style="visibility: visible;">
          <input
            type="checkbox"
            id="load"
            name="mess"
            class="custom-control-input"
            v-model="needLoading"
          />
          <label class="custom-control-label" for="load">Нужна погрузка</label>
        </div>

        <div class="col-md-3" style="visibility: visible;">
          <input
            type="checkbox"
            id="del"
            name="mess"
            class="custom-control-input"
            v-model="form.upToPlace"
          />
          <label class="custom-control-label" for="del"
            >Доставка до места</label
          >
        </div>

        <div class="col-md-3" style="visibility: visible;">
          <input
            type="checkbox"
            id="frag"
            name="mess"
            class="custom-control-input"
            v-model="form.isFragileCargo"
          />
          <label class="custom-control-label" for="frag">Хрупкий груз</label>
        </div>
      </div>
      <div class="row mb-3">
        <div class="form-group col-md-12 col-sm-12">
          <p class="badge badge-warning">Расстояние (км)</p>
          <input
            type="text"
            name="adress"
            id="vol"
            class="form-control"
            placeholder="50 км"
            required=""
            v-model="form.distance"
          />
        </div>
      </div>
      <div class="row col-12 mb-3">
        <span id="out">{{this.form.result}}</span> <span class="dollar">$</span>
      </div>
      <div class="row">
        <div class="col-md-2 col-12">
          <input
            type="button"
            name="adress"
            id="btn"
            class="btn-block btn btn-primary"
            value="Считать"
            v-on:click="calculateHandler"
          />
        </div>
      </div>
    </form>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      form: {
        weight: "",
        size: "",
        needLoading: false,
        upToPlace: false,
        isFragileCargo: false,
        distance: '',
        result:0
      },
    };
  },
  methods: {
    calculateHandler() {
        this.form.result= this.form.weight * this.form.size*this.form.distance + (!!this.form.needLoading ? 50 : 0) + (!!this.form.upToPlace ? 50 : 0) + (!!this.form.isFragileCargo ? 100 : 0)
        this.form.result = this.form.result*0.001
        console.log(this.form);
    }
  }
};
</script>

<style scoped>
.calculator {
  margin-top: 150px;
  padding-bottom: 150px;
}
</style>
