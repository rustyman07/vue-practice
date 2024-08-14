<script >


export default {
  // Properties returned from data() become reactive state
  // and will be exposed on `this`.
  data() {
    return {
      count: 0,
      activePage:0,
      heroes :['Phantom assasin','traxex'],
      isShow: true,
      pages:[{
        url: "index.html",
        title: "HOME"
      },
      {
        url: "about.html",
        title: "ABOUT"
      }
      
      
      ]
    }
  },

  // Methods are functions that mutate state and trigger updates.
  // They can be bound as event handlers in templates.
  methods: {
    increment() {
      this.count++
    },
    toggle(){
      this.isShow = !this.isShow;
    }
  },

  // Lifecycle hooks are called at different stages
  // of a component's lifecycle.
  // This function will be called when the component is mounted.
  mounted() {
    console.log(`The initial count is ${this.count}.`)
  }
}
</script>

<template>
  <ul >
 <li v-for = "(page,index) in pages" key = "index" >

  <a :href="page.url">{{page.title}}</a>
 </li>
  </ul>
  <div  v-if= "isShow" > hello </div>

  <button @click="toggle">Toggle</button>
 

</template>

