<template>
  <div class="nc-demo">
    <!-- use $nclang to get i18n data -->
    <label>{{ $nclang("hi", { name: mergeConfig.name }) }}</label>

    <!-- disabled / readonly / placeholder / hidden : use the computed version, not the config version. -->
    <!-- modelVal: for binding value. -->
    <input
      :disabled="disabled"
      :readonly="readonly"
      :placeholder="placeholder"
      v-show="!hidden"
      v-model="modelVal"
    />
  </div>
</template>

<style lang="scss" scoped>
.nc-demo {
}
</style>

<script>
import ncformCommon from "@ncform/ncform-common";

export default {
  mixins: [ncformCommon.mixins.vue.controlMixin],

  i18nData: {
    // i18n
    en: {
      hi: "Hi <%= name %>"
    },
    zh_cn: {
      hi: "你好 <%= name %>"
    }
  },

  data() {
    return {
      defaultConfig: {
        // your config's default value ( Note: use mergeConfig to get config value )
        name: "daniel"
      }
    };
  },

  methods: {
    // you can handle the modelVal before $emit it ( before this.$emit('input') )
    _processModelVal(modelVal) {
      return modelVal;
    }

    // you can use this.$http to make some http requests ( this.$http is the same as axios )
  }
};
</script>
