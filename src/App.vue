<script setup>
import Home from "./components/Home.vue";
</script>

<template>
  <Home />
</template>

<style lang="scss">
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html,
body {
  max-width: 100vw;
  overflow-x: hidden;
  background-color: var(--bg);
  color: var(--txt);
  font-family: var(--montserrat);
}

a {
  text-decoration: none;
}

.txt {
  &-muted {
    color: var(--muted);
  }
  &-light {
    color: var(--light);
  }
  &-dark {
    color: var(--dark);
  }
  &-red {
    color: var(--red);
  }
  &-green {
    color: var(--green);
  }
  &-yellow {
    color: var(--yellow);
  }
  &-purple {
    color: var(--purple);
  }
  &-orange {
    color: var(--orange);
  }
  &-blue {
    color: var(--blue);
  }
  &-link {
    color: var(--link);
  }
  &-link:hover {
    color: var(--hovered-link);
  }
  &-muted-link {
    color: var(--muted-link);
    cursor: auto;
  }
}
</style>
