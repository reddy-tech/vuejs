<template>
<div>
<img :src="book.imageurl" alt="Property image" class="property-image">
  <ul>
    <li>Address: {{ book.address }}</li>
    <li>Type: {{ book.type }}</li>
    <li>Square Footage: {{ book.squareFootage }} sqft</li>
    <li>Current Price: ${{ book.currentPrice?.toLocaleString() }}</li>
    <li>Price History: 
      <span v-for="(price, index) in book.priceHistory" :key="index">
        ${{ price.toLocaleString() }}<span v-if="index < book.priceHistory.length - 1"> ,</span>
      </span>
    </li>
    <li>Price Per Sqft: ${{ book.pricePerSqft }}</li>
    <li>Crime Rate: {{ book.crimeRate }}</li>
    <li>School Ratings: {{ book.schoolRatings }}/10</li>
    <li>Walkability Score: {{ book.walkabilityScore }}/100</li>
    <li>Yearly Appreciation: {{ book.yearlyAppreciation }}</li>
    <li>Rental Yield: {{ book.rentalYield }}</li>
    <li>Days on Market: {{ book.daysOnMarket }}</li>
    <li>Nearby Transit: {{ book.nearbyTransit }}</li>
    <li>Parks: 
      <span v-for="(park, index) in book.parks" :key="index">
        {{ park }}<span v-if="index < book.parks.length - 1">, </span>
      </span>
    </li>
    <li>Hospitals: 
      <span v-for="(hospital, index) in book.hospitals" :key="index">
        {{ hospital }}<span v-if="index < book.hospitals.length - 1">, </span>
      </span>
    </li>
  </ul>
</div>
</template>
  
  <script>
  
  
   
  
  export default {
    name: 'SingleBook',
    props: {
        book:Object
    }

  }
  
  
  
  
  </script>
  
<style scoped>
div {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  margin: 20px 0;
  padding: 20px;
  transition: transform 0.3s ease;
}

div:hover {
  transform: translateY(-5px);
}

.property-image {
  width: auto;
  max-width: 100%;
  height: auto;
  max-height: 250px;
  object-fit: contain;
  border-radius: 8px;
  margin: 0 auto 20px;
  display: block;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.property-image:hover {
  transform: scale(1.02);
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  padding: 8px 0;
  border-bottom: 1px solid #eee;
}

li:last-child {
  border-bottom: none;
}

li strong {
  color: #2c3e50;
  font-weight: 600;
  margin-right: 5px;
}

.price {
  color: #e74c3c;
  font-weight: bold;
  font-size: 1.2rem;
}

.features {
  display: flex;
  flex-wrap: wrap;
  margin-top: 10px;
}

.feature-item {
  background-color: #eaf2f8;
  border-radius: 20px;
  padding: 5px 12px;
  margin: 5px;
  font-size: 0.9rem;
}
</style>