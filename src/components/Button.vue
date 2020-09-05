<template>
  <div>
    <button
      :class="[`button-${variant}-${color}`, border, buttonSize]"
      class="button flex flex-row justify-center items-center"
    >
      <i v-if="startIcon" class="material-icons mr-2 text-sm">startIcon</i>
      Default
      <i v-if="endIcon" class="material-icons ml-2 text-sm">endIcon</i>
    </button>
  </div>
</template>

<script>
export default {
  props: {
    variant: {
      type: String,
      default: "normal",
    },
    disabled: Boolean,
    disableShadow: Boolean,
    startIcon: String,
    endIcon: String,
    size: String,
    color: {
      type: String,
      default: "default",
    },
  },
  computed: {
    border() {
      return this.variant === "outline" ? "border-2" : "";
    },
    buttonSize() {
      let size = "py-2 pl-3 pr-4";
      switch (this.size) {
        case "md":
          size = "py-3 pl-4 pr-5";
          break;
        case "lg":
          size = "py-4 pl-5 pr-6";
          break;
        default:
          //Declaraciones ejecutadas cuando ninguno de los valores coincide con el valor de la expresión
          break;
      }

      return size;
    },
  },
};
</script>

<style lang="scss" scoped>
.button {
  @apply rounded-lg;
  @apply shadow-md;
  @apply text-gray-800;

  &-normal {
    @apply border-0;

    &-primary {
      @apply bg-primary;
      @apply text-white;
    }
    &-secondary {
      @apply bg-secundary;
      @apply text-white;
    }
    &-default {
      @apply bg-default;
      @apply text-secundary;
    }
    &-danger {
      @apply bg-danger;
      @apply text-white;
    }
  }

  &-outline {
    @apply border-solid;
    @apply border-opacity-100;

    &-primary {
      @apply border-primary;
      @apply text-primary;
    }
    &-secondary {
      @apply border-secundary;
      @apply text-secundary;
    }
  }

  &-text {
    @apply bg-white;
    &-primary {
      @apply text-primary;
      @apply shadow-none;
      @apply p-0;
    }
  }
}

.outline {
  @apply border-2;
}
</style>
