<script setup lang="ts">
  import {ref} from "vue";
  import * as dayjs from "dayjs";

  const todayMonth = dayjs().get('M');
  const year = dayjs().get('year');
  const difference =
      todayMonth < 6 ?
      dayjs(`07.01.${year-1}`).diff(dayjs(), 'd') :
      dayjs().diff(dayjs(`07.01.${year}`), 'd')

  const date = ref(`${todayMonth === 6 ? dayjs().format('dd') : difference} и Юля`)
</script>

<template>
  <h1>{{ date }}</h1>
</template>

<style scoped>

</style>
