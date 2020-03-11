<template>
  <div>
  <child v-bind:val="message"/>
  </div>
</template>

<script>
import child from "./Child"

export default {
    data: () => ({
        message: "Hej Adin"
    }),
    methods: {

    },
    components: {child}


};
</script>

<style>
</style>