<template>
  <nav class="navbar navbar-expand-sm navbar-dark bg-dark">
      <a class="navbar-brand" href="#">energenie</a>
      <button class="navbar-toggler d-lg-none" type="button" data-toggle="collapse" data-target="#collapsibleNavId" aria-controls="collapsibleNavId"
          aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="collapsibleNavId">
          <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
              <li class="nav-item active">
                  <nuxt-link class="nav-link" to="/">Home</nuxt-link>
              </li>
              <li class="nav-item">
                  <nuxt-link class="nav-link" to="gasenergy">Gas M3 > kwH</nuxt-link>
              </li>
              <li class="nav-item dropdown">
                  <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Dropdown</a>
                  <div class="dropdown-menu" aria-labelledby="dropdownId">
                      <a class="dropdown-item" href="#">Action 1</a>
                      <a class="dropdown-item" href="#">Action 2</a>
                  </div>
              </li>
          </ul>
      </div>
  </nav>
</template>

<script>
export default {

}
</script>

<style>

</style>