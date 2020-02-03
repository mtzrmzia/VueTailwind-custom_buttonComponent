<template>
  <div id="app" class="bg-gray-200 min-h-screen">
    <h2 class="ml-6 pt-3 text-lg font-semibold">Simple Buttons</h2>
    <div class="flex flex-wrap p-4">
      <t-button v-for="colors in colors" :color="colors" :key="colors" class="mx-2 mb-2">
        <span class="capitalize">{{colors}}</span>
      </t-button>
    </div>

    <h2 class="ml-6 mt-3 text-lg font-semibold">Outline</h2>
    <div class="flex flex-wrap p-4">
      <t-button v-for="colors in colors" outline :color="colors" :key="colors" class="mx-2 mb-2">
        <span class="capitalize">{{colors}}</span>
      </t-button>
    </div>

    <h2 class="ml-6 mt-3 text-lg font-semibold">Sizes</h2>
    <div class="flex items-end p-4">
      <div v-for="size in sizes" :key="size">
        <t-button :size="size" class="mx-2 mb-2">
          <span class="capitalize">{{size}}</span>
        </t-button>
      </div>
    </div>
    <h2 class="ml-6 mt-3 text-lg font-semibold">Icons</h2>
    <div class="flex flex-wrap items-end p-4">
      <t-button class="mx-2 mb-2">
        <i class="far fa-edit mr-1"/>
        <span>Edit</span>
      </t-button>
      <t-button class="mx-2 mb-2" icon>
        <i class="far fa-edit"/>
      </t-button>
      <t-button class="mx-2 mb-2" icon outline color="red" size="sm">
        <i class="far fa-trash-alt"/>
      </t-button>
      <t-button class="mx-2 mb-2" icon outline color="red">
        <i class="far fa-trash-alt"/>
      </t-button>
      <t-button class="mx-2 mb-2" icon outline color="red" size="lg">
        <i class="far fa-trash-alt"/>
      </t-button>
      <t-button class="mx-2 mb-2" size="sm" icon round outline color="green">
        <i class="fas fa-plus"/>
      </t-button>
      <t-button class="mx-2 mb-2" icon round outline color="green">
        <i class="fas fa-plus"/>
      </t-button>
      <t-button class="mx-2 mb-2" size="lg" icon round outline color="green">
        <i class="fas fa-plus"/>
      </t-button>
    </div>

    <h2 class="ml-6 pt-3 text-lg font-semibold">Link Button</h2>
    <div class="flex flex-wrap p-4">
      <t-button
        v-for="colors in colors"
        :color="colors"
        :key="colors"
        href="https://codesandbox.io"
        class="mx-2 mb-2"
      >
        <span class="capitalize">Link {{colors}}</span>
      </t-button>
    </div>

    <h2 class="ml-6 pt-3 text-lg font-semibold">Click Event Button</h2>
    <div class="flex flex-wrap p-4">
      <t-button
        v-for="colors in colors"
        :color="colors"
        :key="colors"
        @click="fireAlert(colors)"
        class="mx-2 mb-2"
      >
        <span class="capitalize">Click Me {{colors}}</span>
      </t-button>
    </div>
  </div>
</template>

<script>
import TButton from "./components/t-button";

export default {
  name: "App",
  components: {
    TButton
  },
  data() {
    return {
      colors: [
        "gray",
        "yellow",
        "orange",
        "red",
        "green",
        "teal",
        "blue",
        "indigo",
        "purple",
        "pink"
      ],
      sizes: ["lg", "md", "sm"]
    };
  },
  methods: {
    fireAlert(color) {
      alert(`Clicked on ${color}`);
    }
  }
};
</script>
