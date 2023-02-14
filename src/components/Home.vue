<script setup>
import NoteList from "./notes/NoteList.vue";

const name = "Régi Ágnes";
const occupation = "Gyógypedagógus, tanító";
const email = "regiagnes20@gmail.com";
const phone = "+36 30 586-4866";

const notes = [
  {
    variant: "red",
    description: ["artikulációs", "terápia", "(pöszeterápia)"],
  },
  { variant: "green", description: ["olvasás,", "írás", "fejlesztés"] },
  {
    variant: "dark",
    description: ["beszédészlelés,", "beszédértés", "fejlesztés"],
  },
  { variant: "purple", description: ["iskola", "elōkészítés", ""] },
  { variant: "orange", description: ["nyelvlökéses", "nyelés", "terápia"] },
  { variant: "blue", description: ["orrhangzós", "terápia", ""] },
  { variant: "dark", description: ["iskolai", "felzárkóztatás", ""] },
];
</script>

<template>
  <main>
    <section class="title">
      <h1>{{ name }}</h1>
      <h3 class="txt-dark">{{ occupation }}</h3>
    </section>
    <section class="info">
      <table>
        <tr>
          <td>Telefon</td>
          <td>
            <a v-bind:href="`tel:` + phone" class="txt-link">{{ phone }}</a>
          </td>
        </tr>
        <tr>
          <td>emial</td>
          <td>
            <a v-bind:href="`mailto:` + email" class="txt-link">{{ email }}</a>
          </td>
        </tr>
      </table>
    </section>
    <section>
      <h3>Logopédiai szakiránnyal vállalok:</h3>
      <div class="note-list">
        <NoteList :notes="notes" />
      </div>
    </section>
  </main>
</template>

<style scoped lang="scss">
section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 1rem;
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  margin-top: 1rem;
}

.note-list {
  margin-top: 2rem;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 2rem;
}

@media (max-width: 992px) {
  .note-list {
    grid-template-columns: auto;
  }
}

section.note-list h3 {
  margin-bottom: 1rem;
}
</style>
