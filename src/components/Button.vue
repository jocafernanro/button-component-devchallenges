<template>
  <div>
    <button
      :disabled="disabled"
      :class="[disabled ? `disabled-${variant}` : `button button-${variant}-${color}`, border, buttonSize, shadow]"
      class="flex flex-row justify-center items-center noto-font mt-4"
    >
      <i v-if="startIcon" class="material-icons mr-2 text-sm">{{ startIcon }}</i>
      Default
      <i v-if="endIcon" class="material-icons ml-2 text-sm">{{ endIcon }}</i>
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
      let size = "py-2 px-4";

      switch (this.size) {
        case "md":
          size = "py-3 px-6";
          break;
        case "lg":
          size = "py-4 px-8";
          break;
        default:
          //Declaraciones ejecutadas cuando ninguno de los valores coincide con el valor de la expresión
          break;
      }

      return size;
    },
    shadow() {
      return !this.disableShadow && this.variant === "normal" && !this.disabled
        ? "shadow-lg"
        : "";
    },
  },
};
</script>

<style lang="scss" scoped>
.disabled {
  &-normal {
    @apply bg-default;
    @apply text-default-disabled;
    @apply rounded-lg;
  }
  &-outline {
    @apply bg-default;
    @apply text-default-disabled;
    @apply rounded-lg;
  }
  &-text {
    @apply bg-white;
    @apply text-default-disabled;
    @apply px-0;
    @apply py-2;
  }
}

.button {
  @apply rounded-lg;
  @apply text-gray-800;

  &-normal {
    @apply border-0;

    &-primary {
      @apply bg-primary;
      @apply text-white;

      &:hover,
      &:focus {
        @apply bg-primary-darker;
      }
    }
    &-secondary {
      @apply bg-secondary;
      @apply text-white;

      &:hover,
      &:focus {
        @apply bg-secondary-darker;
      }
    }
    &-default {
      @apply bg-default;
      @apply text-secondary;

      &:hover,
      &:focus {
        @apply bg-default-darker;
      }
    }
    &-danger {
      @apply bg-danger;
      @apply text-white;

      &:hover,
      &:focus {
        @apply bg-danger-darker;
      }
    }
  }

  &-outline {
    @apply border-solid;
    @apply border-opacity-100;

    &-primary {
      @apply border-primary;
      @apply text-primary;

      &:hover,
      &:focus {
        @apply bg-primary-lighter;
      }
    }
    &-secondary {
      @apply border-secondary;
      @apply text-secondary;

      &:hover,
      &:focus {
        @apply bg-secondary-lighter;
      }
    }
    &-danger {
      @apply border-danger;
      @apply text-danger;

      &:hover,
      &:focus {
        @apply bg-danger-lighter;
      }
    }
    &-default {
      @apply text-gray-800;
      @apply border-gray-800;

      &:hover,
      &:focus {
        @apply bg-gray-200;
      }
    }
  }

  &-text {
    @apply bg-white;

    &-primary {
      @apply text-primary;
      @apply px-0;
      @apply py-2;

      &:hover,
      &:focus {
        @apply bg-primary-lighter;
        @apply text-primary;
        @apply py-2;
        @apply px-4;
      }
    }
    &-secondary {
      @apply text-secondary;
      @apply px-0;
      @apply py-2;

      &:hover,
      &:focus {
        @apply bg-secondary-lighter;
        @apply text-secondary;
        @apply py-2;
        @apply px-4;
      }
    }
    &-default {
      @apply text-default-darker;
      @apply px-0;
      @apply py-2;

      &:hover,
      &:focus {
        @apply bg-default-lighter;
        @apply text-default-darker;
        @apply py-2;
        @apply px-4;
      }
    }
    &-danger {
      @apply text-danger;
      @apply px-0;
      @apply py-2;

      &:hover,
      &:focus {
        @apply bg-danger-lighter;
        @apply text-danger;
        @apply py-2;
        @apply px-4;
      }
    }
  }
}

.outline {
  @apply border-2;
}
</style>
