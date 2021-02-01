<template>
  <div class="container">
    <h2>{{ $t("guide") }}<br /></h2>
    <p>{{ $t("text") }}</p>
    <h2>{{ $t("formationTitle") }}</h2>
    <p>{{ $t("formationText") }}</p>
    <h2>{{ $t("enviromentTitle") }}</h2>
    <p>{{ $t("enviromentText") }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>
