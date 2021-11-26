<template>
  <header>
      <section class="container-fluid p-3 d-flex align-items-center">
          <div class="col-6 logo-box">
            <img src="../assets/logo (2).png" alt="logo">
          </div>
          <div class="col-6 select-box d-flex justify-content-end">
              <select>
                  <option value="" disabled selected hidden>Choose your genre</option>
                  <option value="">All genres</option>
                  <option value="">Rock</option>
                  <option value="">Pop</option>
                  <option value="">Jazz</option>
                  <option value="">Metal</option>
                  <option value="">Rock</option>
              </select>
          </div>
      </section>
  </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped lang="scss">
@import '@/styles/vars.scss';

header {
    background-color: #2e3a46;
}
img {
    width: 50px;
}

.select-box {
    select {
        background-color: $bg-color;
        color: white;
        border: 1px solid #1DB954;
        padding: 10px 35px;
    }
}
</style>