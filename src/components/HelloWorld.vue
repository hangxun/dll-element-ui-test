<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="ele">
      <el-tooltip content="Show Tooltip">
        <el-button>
          ELEMENT UI TEST
        </el-button>
      </el-tooltip>
    </div>

    <div class="vp">
      <vp content="Show Tooltip" :visible="vpShow" placement="right">
        <button style="margin: 32px; cursor: pointer;" slot="content" @click="vpShow = !vpShow">
          VUE POPPER TEST
        </button>
      </vp>
    </div>
  </div>
</template>

<script>
import Popper from 'vue-popper'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      vpShow: false
    }
  },
  components: {
    vp: {
      mixins: [Popper],
      props: {
        content: String,
        visibleArrow: {
          default: true
        }
      },
      template: `
  <div>
    <div class="popper" v-el:popper v-show="visible">
      <slot></slot>
    </div>
    <div class="rel" v-el:reference>
      <slot name="content">
        <div v-text="content"></div>
      </slot>
    </div>
  </div>
  `
    }
  }
}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
  cursor: pointer
}
</style>
