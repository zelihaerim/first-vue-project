<template>
  <div :class="className">
    <h1>{{ msg }}</h1>
    <p> <!-- <p v-show="show"> -->
    {{show ? content :' '}} 
    For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
      
    
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
    <div> 
      <input type="checkbox" :value="1" v-model="checkboxValue">
      deger = {{checkboxValue}}
    </div>
    <div>
      <button @click="chanceValue()" > click - {{name}} </button>
    
    </div>
    {{fullname}}
    <div v-html = "contentHtml"></div>
    <div v-for="(item, i) in items" :key="'name-'+ i" >
      {{item.name}} - {{item.note}}
    </div>
  </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
      msg: {
        default:'Hello',
        required: true,
        type: String
        },
      usd: Number,
    },
  data(){
    return {
      show: true,
      content: '<h4>My data.</h4>',
      className: 'edit-area',
      contentHtml: '<h4>My data.</h4>',
      items:[
        { name: 'turhan', note: 10},
        { name: 'canberk', note: 10},
        { name: 'ata', note: 10},
    
      ],
      checkboxValue:0,
      name:"canberk"
    }
  },
  computed:{
      value(){
        return this.usd* 9.2;
      }
  },
  methods: {
    chanceValue(){
      this.checkboxValue = !this.checkboxValue
    },
    loglama(val){
      console.log(val)
    }
  },
  watch:{ // parametre olarak 2 parametre alıyor, veya bir ama asagidakilerle ayni adda alır.
    checkboxValue(newValue,oldValue){
      console.log("eskideger: "+oldValue)
      console.log("yenideger: "+newValue)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
}
</style>
