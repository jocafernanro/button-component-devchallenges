<template>
  <div id="app" class="container mx-auto p-2">
    <header class="my-12">
      <h1 class="text-2xl poppins-font font-bold">Buttons</h1>
      <span>Pass the mouse/finger over the '&:hover, &:focus' labeled buttons</span>
    </header>
    <section>
      <ButtonGroup width="1/2">
        <div>
          <ButtonLabel>&lt;Button /&gt;</ButtonLabel>
          <Button></Button>
        </div>
        <div>
          <ButtonLabel>&:hover, &:focus</ButtonLabel>
          <Button id="default-hover"></Button>
        </div>
      </ButtonGroup>

      <ButtonGroup width="1/2">
        <div>
          <ButtonLabel>&lt;Button variant=”outline” /&gt;</ButtonLabel>
          <Button :variant="variant.outline" :color="color.primary"></Button>
        </div>
        <div>
          <ButtonLabel>&:hover, &:focus</ButtonLabel>
          <Button :variant="variant.outline" :color="color.primary"></Button>
        </div>
      </ButtonGroup>

      <ButtonGroup width="1/2">
        <div>
          <ButtonLabel>&lt;Button variant=”text” /&gt;</ButtonLabel>
          <Button :variant="variant.text" :color="color.primary"></Button>
        </div>
        <div>
          <ButtonLabel>&:hover, &:focus</ButtonLabel>
          <Button :variant="variant.text" :color="color.primary"></Button>
        </div>
      </ButtonGroup>

      <div class="mb-6">
        <ButtonLabel>&lt;Button disableShadow /&gt;</ButtonLabel>
        <Button :color="color.primary" disableShadow></Button>
      </div>

      <ButtonGroup width="1/2">
        <div>
          <ButtonLabel>&lt;Button disabled /&gt;</ButtonLabel>
          <Button disabled></Button>
        </div>
        <div>
          <ButtonLabel>&lt;Button variant=”text” disabled /&gt;</ButtonLabel>
          <Button :variant="variant.text" disabled></Button>
        </div>
      </ButtonGroup>

      <ButtonGroup width="1/2">
        <div>
          <ButtonLabel>&lt;Button startIcon=”ladd_shopping_cart” /&gt;</ButtonLabel>
          <Button :color="color.primary" startIcon="add_shopping_cart"></Button>
        </div>
        <div>
          <ButtonLabel>&lt;Button endIcon=”add_shopping_cart” /&gt;</ButtonLabel>
          <Button :color="color.primary" endIcon="add_shopping_cart"></Button>
        </div>
      </ButtonGroup>

      <ButtonGroup width="2/3">
        <div>
          <ButtonLabel>&lt;Button size=”sm /&gt;</ButtonLabel>
          <Button :color="color.primary" size="sm"></Button>
        </div>
        <div>
          <ButtonLabel>&lt;Button size=”md" /&gt;</ButtonLabel>
          <Button :color="color.primary" size="md"></Button>
        </div>
        <div>
          <ButtonLabel>&lt;Button size=”lg" /&gt;</ButtonLabel>
          <Button :color="color.primary" size="lg"></Button>
        </div>
      </ButtonGroup>

      <ButtonGroup width="full">
        <div>
          <ButtonLabel>&lt;Button color=”default” /&gt;</ButtonLabel>
          <Button :color="color.default"></Button>
        </div>
        <div>
          <ButtonLabel>&lt;Button color=”primary” /&gt;</ButtonLabel>
          <Button :color="color.primary"></Button>
        </div>
        <div>
          <ButtonLabel>&lt;Button color=”secondary” /&gt;</ButtonLabel>
          <Button :color="color.secondary"></Button>
        </div>
        <div>
          <ButtonLabel>&lt;Button color=”danger” /&gt;</ButtonLabel>
          <Button :color="color.danger"></Button>
        </div>
      </ButtonGroup>
      <ButtonLabel>&:hover, &:focus</ButtonLabel>
      <ButtonGroup width="full">
        <Button :color="color.default"></Button>
        <Button :color="color.primary"></Button>
        <Button :color="color.secondary"></Button>
        <Button :color="color.danger"></Button>
      </ButtonGroup>
    </section>
    <footer class="mt-16 mb-6 text-gray-500 text-sm">josematico.com @jocafernanro</footer>
  </div>
</template>

<script>
import Button from "@/components/Button.vue";
import ButtonLabel from "@/components/ButtonLabel.vue";
import ButtonGroup from "@/components/ButtonGroup.vue";

export default {
  name: "App",
  components: {
    Button,
    ButtonLabel,
    ButtonGroup,
  },
  data: () => {
    return {
      variant: {
        default: "default",
        outline: "outline",
        text: "text",
      },
      color: {
        default: "default",
        primary: "primary",
        secondary: "secondary",
        danger: "danger",
      },
      size: {
        sm: "sm",
        md: "md",
        lg: "lg",
      },
    };
  },
  mounted() {
    document.getElementById("default-hover").focus();
  },
};
</script>

<style>
:root {
  --global-font-family: "Noto Sans JP", "Helvetica Neue", -apple-system,
    BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
  --global-secondary-font-family: "Ubuntu Mono", "Helvetica Neue", -apple-system,
    BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
  --global-title-font-family: "Poppins", "Helvetica Neue", -apple-system,
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
  font-family: var(--global-secondary-font-family);
}

.noto-font {
  font-family: var(--global-font-family);
}

.poppins-font {
  font-family: var(--global-title-font-family);
}
</style>
