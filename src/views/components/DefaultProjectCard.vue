<template>
  <div class="mb-4 col-12 mb-xl-0">
    <div class="card card-blog card-plain">
      <div class="card-header p-0 mt-n4 mx-3">
        <a class="shadow-xl d-block border-radius-xl">
          <img :src="image" alt="img-blur-shadow" class="shadow img-fluid border-radius-xl w-100 h-auto" />
        </a>
      </div>
      <div class="p-3 card-body">
        <p class="mb-0 text-sm text-gradient text-dark">{{ label }}</p>
        <a href="javascript:;">
          <h5>{{ title }}</h5>
        </a>
        <p class="mb-4 text-sm">
          {{ description }}
        </p>
        <div class="d-flex align-items-center justify-content-between">
          <button type="button" class="mb-0 btn btn-sm" :class="`btn-outline-${action.color}`"
            @click="handleActionClick">
            {{ action.label }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DefaultProjectCard",
  props: {
    image: {
      type: String,
      default: "",
    },
    label: {
      type: String,
      default: "",
    },
    title: {
      type: String,
      default: "Default Project Card",
    },
    description: {
      type: String,
      default: "",
    },
    action: {
      type: Object,
      default: () => ({
        color: '',
        label: '',
        url: ''
      }),
    },
    authors: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    handleActionClick() {
      if (this.action.url) {
        window.open(this.action.url);
      }
    }
  }
};
</script>