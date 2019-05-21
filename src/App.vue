<template>
  <div>
    <ncform
      :form-schema="formSchema"
      form-name="your-form-name"
      v-model="formSchema.value"
      @submit="submit()"
    ></ncform>
    <hr />
    <el-button @click="submit()">Submit</el-button>
  </div>
</template>

<script>
import NcDemo from "./components";

export default {
  created() {
    this.$ncformAddWidget({ name: "nc-demo", widget: NcDemo });
  },
  data() {
    return {
      formSchema: {
        type: "object",
        properties: {
          demo: {
            type: "string",
            ui: {
              widget: "nc-demo"
            }
          }
        },
        value: {}
      }
    };
  },
  methods: {
    submit() {
      this.$ncformValidate("your-form-name").then(data => {
        if (data.result) {
          console.log(this.$data.formSchema.value);
        }
      });
    }
  }
};
</script>
