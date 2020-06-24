<template>
    <section>
    <div class="row">
        <div class="col-sm-12">
            <p id="test">
                This is a big old testing test page. Been a fucking nightmare so far
            </p>
        </div>
    </div>
    <div class="row">
        <div class="col-sm-12 d-flex justify-content-center">
            <form action="">
            <input type="text" name="first" v-model="first" @change="combineFunction">
            <input type="text" name="last" v-model="last" @change="combineFunction">
            <button type="submit" class="btn btn-primary">Submit</button>
            <div class="class m-2">
                <p>Value: {{ test }}</p>
            </div>
            </form>
        </div>
    </div>
    <div class="row">
        <div class="col-sm-12 d-flex justify-content-center">
            <form>
            <div class="form-group">
                <label for="kWhReading">Opening Reading</label>
                <input type="number" name="gas-open" id="gas-open" v-model="gasOpen">
            </div>
            <div class="form-group">
                <label for="kWhReading">Closing Reading</label>
                <input type="number" name="gas-close" id="gas-close" v-model="gasClose">
            </div>
            <div class="form-group">
                <label for="kWhReading">Gas M3 Total</label>
                <input type="number" name="gas-m3" id="gas-m3" v-model="gasM3">
            </div>
            <div class="form-group">
                <label for="calValue">Calorific Value</label>
                <input type="number" name="gas-cal" id="gas-cal" v-model="gasCal">
            </div>
            <div class="m-2">
                kWh Consumption: {{ gasKwh }}
            </div>
            </form>
        </div>
    </div>
    </section>
</template>

<script>
export default {
    layout: 'testing',
    transition: 'test',
    methods: {
        doMaths: function() {
            alert('nooooo')
        },
        tryme () {
            console.log('moobaa')
        },
        combineFunction: function() {
            var v = this;
                v.test = v.first.concat(v.last);
        },
    },
    head: {
        title: 'Moobaa'
    },
    data () {
        return {
            "msg": "hello",
            "first": '',
            "last": '',
            "test": '',
            "confactor": '1.02264',
            "gasCal": '39.9',
            "convFactor": '3.6',
            "gasOpen": '',
            "gasClose": ''
    }
    },
    computed: {
        gasKwh: function() {
            return this.gasM3 * this.confactor * this.gasCal / this.convFactor
        },
        gasM3: function() {
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