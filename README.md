# Task4
HTML
<h1>
Components for Building a PC 
</h1>
<div id="app">
  <ul>
    <li v-for="product in products">
      {{ product.name }} - {{ product.price | discount(25) | currency }}
    </li>
  </ul>
</div>
JavaScript/Vue
Vue.filter('discount', function (value, discount) {
	return value * ((100 - discount) / 100);
})

Vue.filter('currency', function (value) {
	return '$' + value.toFixed(2)
})

new Vue({
	el: '#app',
  data: {
  	products: [
      {name: 'Processor', price: 180},
      {name: 'MotherBoard', price: 175},
      {name: 'Memory', price: 95},
      {name: 'GPU', price: 500},
      {name: '250GB SSD', price: 90},
      {name: 'Power Supply', price: 100},
      {name: 'monitor', price: 120}
    ]
  }
})
