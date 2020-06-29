<template>
    <section>
    <div class="row text-center">
        <div class="col-sm-12 mb-3">
            <h1>Gas Consumption to killowatt-hours</h1>
        </div>
    </div>
    <div class="row">
        <div class="col-sm-12 d-flex justify-content-center align-text-center mb-3">
            <b-form-group>
                <b-form-radio-group
                id="meter-radios"
                v-model="selected"
                :options="options"
                buttons
                button-variant="outline-primary"
                name="radios-metering"
                ></b-form-radio-group>
            </b-form-group>
        </div>
    </div>
    <div class="row">
        <div class="col-sm-12 d-flex justify-content-center text-center">
            <form>
            <div class="form-group">
                <label for="kWhReading">Opening Reading</label>
                <input type="number" name="gas-open" class="form-control" id="gas-open" v-model="gasOpen">
            </div>
            <div class="form-group">
                <label for="kWhReading">Closing Reading</label>
                <input type="number" name="gas-close" class="form-control" id="gas-close" v-model="gasClose">
            </div>
            <div class="form-group">
                <label for="kWhReading">Gas Total</label>
                <input type="number" name="gas-tot" class="form-control" id="gas-tot" v-model="gasTot">
            </div>
            <div class="form-group">
                <label for="calValue">Calorific Value</label>
                <input type="number" name="gas-cal" class="form-control" id="gas-cal" v-model="gasCal">
            </div>
            <div class="m-2">
                kWh Consumption: {{ gasKwh }} Mode: {{ selected }}
            </div>
            </form>
        </div>
    </div>
    </section>
</template>

<script>
export default {
    layout: 'default',
    transition: 'test',
    head: {
        title: 'Moobaa'
    },
    data () {
        return {
            "selected": 'm3',
            "confactor": '1.02264',
            "cubic": '0.0283',
            "gasCal": '39.9',
            "convFactor": '3.6',
            "gasOpen": '',
            "gasClose": '',
        options: [
            { text: 'M3', value: 'm3'},
            { text: 'cuft', value: 'cuft'}
        ]}
    },
    computed: {
        gasKwh: function() {
            if (this.selected = 'm3') {
                return this.gasTot * this.confactor * this.gasCal / this.convFactor
            } else if (this.selected = 'cuft') {
                return this.gasTot * this.cubic * this.confactor * this.gasCal / this.convFactor
            }
        },
        gasTot: function() {
            return this.gasClose - this.gasOpen
        }
    }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: grey;
}

#test {
    text-align: center;
}
</style>