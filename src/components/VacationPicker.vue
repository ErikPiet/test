<template>
    <div class="container">
        <h1>{{ header }}</h1>
        <ul>
            <li @click="msgbox(country.name)" class="list-group-item" v-for="country in countryData.countries" :key="country.id" :title="country.details">
                {{ country.id }} - 
                {{ country.name }}
            </li>
        </ul>
        <span v-text="msg"></span>
        <h3>Teller: {{ counter }}</h3>
        <button @click="increment()" class="btn btn-success">+</button>
        <button @click="decrement()" class="btn btn-danger">-</button>
        <hr>
        <!--        Oefening 3.5-->
                <h3><label for="list1">Kies een getal</label></h3>
               <select name="list1" id="list1">
                   <option v-for="(num, index) in numbers"
                            :value="num"
                            :key="index">{{num}}
                    </option>
                </select>
    </div>
</template>

<script>
import countryData from '@/data/CountryData'
export default {
    name: "VacationPicker",
    data() {
        return  {
            countryData,
            msg: 'dit veld heeft een v-text msg',
            header: 'Vue Vacation Picker',
            counter: 0,
            numbers: [10, 20, 30, 40, 50]
        }
    },
    methods: {
        increment() {
            this.counter++;
        },
        decrement() {
            this.counter--;
        },
        msgbox(name) {
            alert("Je hebt op " + name + " geklikt!");
        }
    },
   
}
</script>