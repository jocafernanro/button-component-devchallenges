<template>
  <div id="app">
    <header>
      Buttons
    </header>
    <section>
      <ButtonLabel></ButtonLabel>
      <Button size="sm" color="danger"></Button>
    </section>
    <footer></footer>
  </div>
</template>

<script>
import Button from "@/components/Button.vue";
import ButtonLabel from "@/components/ButtonLabel.vue";
export default {
  name: "App",
  components: {
    Button,
    ButtonLabel,
  },
};
</script>

<style>
:root {
  --global-font-family: "Noto Sans JP", "Helvetica Neue", -apple-system,
    BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
  --global-secundary-font-family: "Ubuntu Mono", "Helvetica Neue", -apple-system,
    BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
  --global-font-size: 1rem;
  --font-weight-regular: 400;
  --font-weight-bold: 700;
}
html,
body {
  font-family: var(--global-font-family);
  font-size: 16px;
  font-weight: var(--font-weight-regular);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

.ubuntu-font {
  font-family: var(--global-secundary-font-family);
}

.noto-font {
  font-family: var(--global-font-family);
}
</style>
