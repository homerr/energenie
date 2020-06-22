<template>
    <section>
    <div class="row">
        <div class="col-sm-12">
            <p id="test">
                This is a big old testing test page. Been a fucking nightmare so far
            </p>
        </div>
    </div>
    <div class="row align-items-center">
        <div class="col-sm-12"><form action="">
            <input type="text" name="test">
            <button type="submit" class="btn btn-primary">Submit</button>
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
        }
    },
    head: {
        title: 'Moobaa'
    },
    data () {
        return {
            "msg": "hello"
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