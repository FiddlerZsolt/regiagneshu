<script setup>
defineProps({
  note: Object,
});
</script>

<template>
  <div class="note" :class="note.variant ? `txt-${note.variant}` : ''">
    <div v-for="desc in note.description" class="row">
      {{ desc }}
    </div>
  </div>
</template>

<style scoped lang="scss">
.note {
  --scale: 1.1;
  background-color: var(--note-bg);
  position: relative;
  padding: 1rem 2rem;
  margin-bottom: 1.5rem;
  max-width: 250px;
  margin-inline: auto;
  transition: 150ms ease-in-out;
  font-family: var(--hand);
  font-size: 1.5rem;

  // Vertical red line
  &::before {
    content: "";
    position: absolute;
    top: 5%;
    left: 2rem;
    height: 90%;
    width: 2px;
    background-color: var(--note-vertical-line);
  }

  // Tape
  &::after {
    content: "";
    position: absolute;
    top: -12%;
    left: 45%;
    height: 30px;
    width: 20px;
    background-color: var(--yellow);
  }

  &:nth-child(odd) {
    rotate: 5deg;
    &::after { rotate: 8deg; }
  }

  &:nth-child(even) {
    rotate: -5deg;
    &::after { rotate: -8deg; }
  }

  &:hover {
    rotate: 0deg;
    scale: var(--scale);
  }

  .row {
    --margin: 22px;
    position: relative;
    padding: 0.3rem;
    min-height: 30px;
    width: 100%;
    text-transform: capitalize;

    // Horizontal blue line
    &::before {
      content: "";
      position: absolute;
      bottom: 6px;
      left: calc(var(--margin) * -1);
      height: 1px;
      width: calc(100% + calc(var(--margin) * 2));
      background-color: var(--note-horizontal-line);
    }

    // Dots
    &:nth-child(odd) {
      &::after {
        --size: 15px;
        content: "";
        position: absolute;
        bottom: calc(var(--margin) / 1.6);
        left: calc(var(--margin) * -0.9);
        height: var(--size);
        width: var(--size);
        background-color: var(--bg);
        border-radius: 50%;
      }
    }
  }
}
</style>
