<script setup>
import { Icon } from "@iconify/vue";
</script>

<template>
  <nav class="icon-grid">
    <span class="icon">
      <Icon icon="ci:folder-code" />
      <span>Meu computador</span>
    </span>
    <span class="icon">
      <Icon icon="ci:folder-document" />
      <span>Meus documentos</span>
    </span>
    <!-- <span class="icon">
      <Icon icon="logos:adobe-premiere" />
      <span>Adobe Premiere 2025</span>
    </span>
    <span class="icon">
      <Icon icon="logos:adobe-photoshop" />
      <span>Adobe Photoshop 2025</span>
    </span>
    <span class="icon">
      <Icon icon="logos:adobe-illustrator" />
      <span>Adobe Illustrator 2025</span>
    </span>
    <span class="icon">
      <Icon icon="vscode-icons:file-type-word" />
      <span>Word</span>
    </span>
    <span class="icon">
      <Icon icon="vscode-icons:file-type-excel" />
      <span>Excel</span>
    </span>
    <span class="icon">
      <Icon icon="vscode-icons:file-type-powerpoint" />
      <span>PowerPoint</span>
    </span> -->
  </nav>
</template>

<style scoped>
.icon-grid {
  padding: 1em 1.2em;
  display: flex;
  flex-wrap: wrap;
  gap: .8em;
}

.icon {
  border: 2px solid #00000000;
  flex-direction: column;
  border-radius: .5em;
  height: min-content;
  align-items: center;
  text-align: center;
  display: flex;
  padding: .3em;
  width: 6em;
  gap: .4em;
}

.icon:hover {
  background-color: #bababa20;
  border: 2px solid #bababa40;
}

.icon:active {
  background-color: #bababa40;
  border: 2px solid #bababa60;
}

.icon svg {
  font-size: 3.2em;
}

.icon span {
  text-shadow: 2px 2px 2px black;
  font-size: .9rem;
}
</style>