<template>
  <div class="container-fluid calculator">
    <h1>CalcuLATER</h1>
    <div class="row output justify-content-center">
      {{display}}
    </div>
    <div class="row justify-content-center">
      <div class="btn-group">
        <button type="button" id="clearBtn" class="btn btn-primary" @click="Clear">C</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Divide">/</button>
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="btn-group">
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Seven">7</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Eight">8</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Nine">9</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Multiply">*</button>
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="btn-group">
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Four">4</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Five">5</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Six">6</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Subtract">-</button>
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="btn-group">
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="One">1</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Two">2</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Three">3</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Plus">+</button>
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="btn-group">
        <button type="button" id="zeroBtn" class="btn btn-outline-dark" @click="Zero">0</button>
        <button type="button" id="calcBtn" class="btn btn-outline-dark" @click="Dot">.</button>
        <button type="button" id="calcBtn" class="btn btn-primary" @click="Equal">=</button>
      </div>
    </div>
  </div>
</template>

<script>
  export default{
    data: function() {
      return {
      display: '0',
      firstTemp: '',
      secondTemp:'',
      totalTemp:'',
      newNumber: false,
      operator: null
      }
    },
    methods: {
      Zero: function() {
        if (this.display != 0){
        this.display += '0';
        }
        else{
        return;
        }
      },
      One: function() {
        this.firstTemp = '1';
        if (this.display == 0 || this.newNumber == true){
        this.display = this.firstTemp;
        this.newNumber = false;
        }
        else{
        this.display += this.firstTemp;
        }
      },
      Two: function() {
        this.firstTemp = '2';
        if (this.display == 0 || this.newNumber == true){
        this.display = this.firstTemp;
        this.newNumber = false;
        }
        else{
        this.display += this.firstTemp;
        }
      },
      Three: function() {
        this.firstTemp = '3';
        if (this.display == 0 || this.newNumber == true){
        this.display = this.firstTemp;
        this.newNumber = false;
        }
        else{
        this.display += this.firstTemp;

        }
      },
      Four: function() {
        this.firstTemp = '4';
        if (this.display == 0 || this.newNumber == true){
        this.display = this.firstTemp;
        this.newNumber = false;
        }
        else{
        this.display += this.firstTemp;

        }
      },
      Five: function() {
        this.firstTemp = '5';
        if (this.display == 0 || this.newNumber == true){
        this.display = this.firstTemp;
        this.newNumber = false;
        }
        else{
        this.display += this.firstTemp;
        }
      },
      Six: function() {
        this.firstTemp = '6';
        if (this.display == 0 || this.newNumber == true){
        this.display = this.firstTemp;
        this.newNumber = false;
        }
        else{
        this.display += this.firstTemp;
        }
      },
      Seven: function() {
        this.firstTemp = '7';
        if (this.display == 0 || this.newNumber == true){
        this.display = this.firstTemp;
        this.newNumber = false;
        }
        else{
        this.display += this.firstTemp;
        }
      },
      Eight: function() {
        this.firstTemp = '8';
        if (this.display == 0 || this.newNumber == true){
          this.display = this.firstTemp;
          this.newNumber = false;
        }
        else{
          this.display += this.firstTemp;
        }
      },
      Nine: function() {
        this.firstTemp = '9';
        if (this.display == 0 || this.newNumber == true){
        this.display = this.firstTemp;
        this.newNumber = false;
        }
        else{
        this.display += this.firstTemp;
        }
      },
      Dot: function() {
        if (this.display != 0){
          this.display += '.';
        }
        else{
          return;
        }
      },
      Plus: function() {
        this.operator = '+';
        this.secondTemp = parseFloat(this.display);
        this.newNumber = true;
      },
      Subtract: function() {
        this.operator = '-';
        this.secondTemp = parseFloat(this.display);
        this.newNumber = true;
      },
      Multiply: function() {
        this.operator = '*';
        this.secondTemp = parseFloat(this.display);
        this.newNumber = true;
      },
      Divide: function() {
        this.operator = '/';
        this.secondTemp = parseFloat(this.display);
        this.newNumber = true;
      },
      Clear: function() {
        this.display = 0;
        this.firstTemp = '';
        this.secondTemp = '';
        this.totalTemp = '';
        this.operator = null;
        this.newNumber = true;
      },
      Equal: function() {
        this.firstTemp = parseFloat(this.display);
        switch(this.operator){
          case '+':
          this.display = (this.secondTemp + this.firstTemp);
          this.newNumber = true;
          break;
          case '-':
          this.display = (this.secondTemp - this.firstTemp);
          this.newNumber = true;
          break;
          case '*':
          this.display = (this.secondTemp * this.firstTemp);
          this.newNumber = true;
          break;
          case '/':
          this.display = (this.secondTemp / this.firstTemp);
          this.newNumber = true;
          break;
          default: 
            return;
        }
      }
    }
  }
</script>

<style>
h1{
  text-align: center;
  font-size: 3em;
}
body{
  width: 600px;
  margin: 4% auto;
}
  .calculator{
    padding: 20px;
    box-shadow: 0px 1px 4px 0px rgba(0, 0, 0, 0.2);
    border-radius: 1px;
    background-color: #F5F5F5
  }
  .output{
    text-align: right;
    font-size: 2em;
  }
  .btn{
    margin: 10px;
  }
  .btn:hover{
    background-color: #D0D0D0 !important;

  }
  #calcBtn{
    padding: 10px 20px;
    border-radius: 5px;
  }
  #zeroBtn{
    padding: 10px 55px;
  }
  #clearBtn{
    margin-right: 130px;
    padding: 10px 20px
  }
</style>
