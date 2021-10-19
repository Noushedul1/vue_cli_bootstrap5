<template>
  <p>{{fname}}</p>
  <Bs />
  <h1>My father name is :{{parents[0]}}</h1>
  <h2>My mother name is :{{parents[1]}}</h2>
  <a v-bind:href="src">click</a>
  <p v-text="country"></p>
  <div v-html="htmltag">
      
  </div>
  <div>
    <p v-if="adult <= 13">
      You can go now
    </p>
    <p v-else>
      You can not go there
    </p>
  </div>
  <div>
  <div v-if="mature >= 19">
    You are little mature
  </div>
  <div v-else>
    You are more mature
  </div>
  </div>
  <div>
    <div v-show="adult < mature">
      You are adult
    </div>
    <div v-show="adult > mature">
      You are Mature
    </div>
  </div>
  <button @click="add">Click here</button>
  <p>{{addition()}}</p>
  <div>
    <p>My High School : {{details.school}}</p>
    <p v-once>My City : {{details.school}}</p>
    {{detailsUpdate()}}
  </div>
  <form v-on:submit.prevent='ourdata'>
    <label>first name</label>
    <input type="text" v-model="formsdata.firstName">
    <label>Second name</label>
    <input type="text" v-model="formsdata.secondName">
    <br>
    <button type="submit" class="ctn btn-primary">Submit</button>
  </form>
  <div v-for="a in favouriteFood" :key="a">
    <ul>
      <li class="border">{{a}}</li>
    </ul>
  </div>
  <ComFirstprops v-bind:mygame="details.city"/>
  <ComMyarray :myarr="favouriteFood"/>
  <div>
    <p>{{fname}}</p>
    <button class="btn btn-primary" v-on:click="mynameChange('noushedul islam akib')">name change</button>
  </div>
  <i class="bi bi-alarm"></i>
  <div class="border bg-primary text-white p-3" v-on:mousemove="valueChange">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident facilis deserunt delectus sapiente ad? Quo cumque iure id ab voluptatem porro non suscipit quisquam! Delectus amet voluptatibus officiis non itaque.
  </div>
  <p>x : {{x}}</p>
  <p>y : {{y}}</p>
</template>
<script>
import Bs from './components/Bs.vue';
import ComFirstprops from './components/Firstprops.vue';
import ComMyarray from './components/Myarray.vue';
export default{
  components: {Bs,ComFirstprops,ComMyarray},
  data(){
    return{
      fname: "noushed",
      age: 25,
      parents: ['Mohi Uddin','Hosneara Begum'],
      details: {
        village: 'Idilpur',
        school: 'mirzarhat',
        city: 'chittagong'
      },
      src: 'https://getbootstrap.com/docs/5.0/getting-started/download/',
      htmltag: '<h3>hello awesome people',
      country: 'Bangladesh',
      mature: 20,
      adult: 18,
      x: '',
      y: '',
      formsdata: {
        firstName: '',
        secondName: ''
      },
      favouriteFood: ['apple','sweet','biriyani']
    }
  },
  methods: {
    add(){
      console.log(this.country);
    },
    addition(){
      return 10+10;
    },
    detailsUpdate(){
      setTimeout(()=>{
        this.details.school = 'Mirzar Hat High School';
      },2000);
    },
    ourdata(){
      // console.log(this.formsdata);
      console.log(`first name is : ${this.formsdata.firstName} and second name is : ${this.formsdata.secondName}`);
    },
    mynameChange(a){
      this.fname = a;
    },
    valueChange(event){
      this.x = event.clientX;
      this.y = event.clientY;
    }
  }
}
</script>
<style scoped>

</style>
