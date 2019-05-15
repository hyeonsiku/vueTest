<template>
  <div>
    <v-text-field v-model="object.title"></v-text-field>
    <v-text-field v-model="object.titleEnglish"></v-text-field>
    <v-btn @click="changeObject">수정</v-btn>
  </div>
</template>

<script>
export default {
  props: ["title", "titleEnglish"],
  data() {
    return {
      object: {}
    };
  },
  created() {
    this.object.title = this.title;
    this.object.titleEnglish = this.titleEnglish;
  },
  methods: {
    changeObject() {
      this.$emit("childObject", this.object);
    }
  }
};
</script>
