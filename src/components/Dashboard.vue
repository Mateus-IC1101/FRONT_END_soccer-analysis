<template>
  <div>xxsx {{ data }}</div>
</template>

<script>
export default {
  mounted() {
    this.getList();
  },
  data() {
    return {
      data: {},
    };
  },
  methods: {
    getList() {
      this.axios.defaults.headers.get["Access-Control-Allow-Origin"] = "*";
      this.axios.get("http://127.0.0.1:5000/users").then((response) => {
        console.log(response.data);
        this.data = response.data;
      });
    },
  },
};
</script>
