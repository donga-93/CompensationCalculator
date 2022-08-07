<template>
<section id="content">
<h2>Quam Tristique Condimentum</h2>
<p>Duis mollis, est non commodo luctus, nisi erat porttitor ligula, 
 eget lacinia odio sem nec elit. Cum sociis natoque penatibus et magnis dis parturient montes,
 nascetur ridiculus mus. <span id="c">Curabitur blandit</span> tempus porttitor. Integer posuere erat a ante venenatis dapibus posuere velit aliquet.
 Vestibulum id ligula porta felis euismod semper.</p>
 <h3>Fringilla Euismod Adipiscing Ipsum</h3>
<h5>Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas faucibus mollis interdum. Aenean lacinia bibendum nulla sed.</h5>
<img src="./assets/Image.png" />

<dl>
  <dt><button id="t"></button> Tellus Ullamcorper Inceptos</dt>
  <dt><button id="m"></button> Magna Condimentum</dt>
  <dd><button id="m2"></button> Mattis Tristique</dd>
  <dd><button id="p"></button> Pharetra Pellentesque Dapibus</dd>
  <dt><button id="a"></button> Aenean Inceptos</dt>
  <dt><button id="p2"></button> Parturient Bibendum</dt>
</dl>
</section>

<section id="calculator">

    <h4 id="compensation">Compensation</h4>
    <h4 id="compensation2">Calculator</h4>

    <label id="inputlabel">Average income</label><br>
    <input placeholder="Salary" name="salary" v-model="salary" type="number"  id="average" ><br>
    <label id="inputlabel2">Days on sick-leave</label><br>
    <input placeholder="Max duration insurance is 182 days" name="days" min=0 max=240 v-model="days" type="number" id="average2" ><br>
    <p id="have">I have tubercolosis</p>
    <input  name="tub" @click="myFunction" v-model="tub" id="check" type="checkbox" />
    <button @click="handle" id="btn">Calculate</button>

 <p id="euro">€</p>
 <p id="ds">days</p>

<div id="result1">
  <p id="employer">The employer compensates</p>
  <p id="days">0 days</p>
  <p id="ds2"></p>
  <p id="amount">0,00$</p>
  <p id="daily">Daily allowance</p>
  <p id="last">00.00€</p>
</div>

<div id="result2">
  <p id="health">Health Insurance compensates</p>
  <p id="days2">0 days</p>
  <p id="zero">0,00$</p>
  <p id="daily2">Daily allowance</p>
  <p id="last2">00.00€</p>
</div>

<div id="total">
 <p id="comp">Compensation total for {{days}} days (net)</p>
 <h2 id="tot"></h2>
</div>

</section>
</template>



<script>
export default {
  name: 'App',
  data() {
    return {
      salary : '',
      days : '',
      euro : '€',
      days2: 'days',
      tub: false
    }
  },
  methods: {
    handle: function() {
      if(this.salary === '' || this.days === '') {
        alert('Please fill Average income or Days on sick-leave');
      }
      else {
      if(this.days !== 4 && this.days !== 5 && this.days !== 6 && this.days !== 7 && this.days !== 8 && this.days !== 9 && this.days !== 10 
      && this.days !== 11 && this.days !== 12 && this.days !== 13 && this.days !== 14) {
        alert('Employer pays the compensation from the 4th to the 8th day')
      }
      else {
        if(this.days === 4 || this.days === 5 || this.days === 6 || this.days === 7 || this.days === 8) {
          document.getElementById("days").innerHTML = this.days + this.days2;
          let result = this.salary / 100 * 70;
          let finish = result / this.days;
          let finish2 = finish / this.days;
          document.getElementById("last").innerHTML = finish2.toFixed(2) + this.euro;
          document.getElementById("amount").innerHTML = finish.toFixed(2) + this.euro;
          document.getElementById("tot").innerHTML = finish.toFixed(2) + this.euro;
        }
        else if(this.days === 9 || this.days === 10 || this.days === 11 || this.days === 12 || this.days === 13 || this.days === 14) {
           document.getElementById("days2").innerHTML = this.days + this.days2;
           let result = this.salary / 100 * 70;
           let finish = result / this.days;
           let finish2 = finish / this.days;
           document.getElementById("last2").innerHTML = finish2.toFixed(2) + this.euro;
           document.getElementById("zero").innerHTML = finish.toFixed(2) + this.euro;
           document.getElementById("tot").innerHTML = finish.toFixed(2) + this.euro;
        }

        }
      }
    },
    myFunction: function() {
     var checkBox = document.getElementById("check");
     if(checkBox.checked) {
       document.getElementById("average2").placeholder = "For tuberculosis it is up to 240 days.";
       console.log('true')
     }
      else  {
      document.getElementById("average2").placeholder = "Max duration insurance is 182 days";
      console.log('false')
      }
    }
  }

}
</script>



<style>
@import './assets/css/style.css';
</style>
