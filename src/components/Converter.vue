<template>
    <div class="converter">
        <h2>{{currencyA}} Para {{currencyB}}</h2>
        <input type="text" v-model="currencyA_value" v-bind:placeholder="currencyA">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{currencyB_value}}</h2>
    </div>
</template>

<script>
export default {
    name: "Converter",
    props: ["currencyA", "currencyB"],
    data() {
        return {
            currencyA_value: "",
            currencyB_value: 0
        };
    },
    methods: {
        converter() {
            let fromTo = `${this.currencyA}_${this.currencyB}`;
            let apiKey = "99c6c90cd10341e18619";
            let url = `https://free.currconv.com/api/v7/convert?q=${fromTo}&compact=ultra&apiKey=${apiKey}`;
            fetch(url).then(response => { return response.json(); }).then(json => {
                let price = json[fromTo];
                this.currencyB_value = (price * parseFloat(this.currencyA_value)).toFixed(2);
            })
        }
    }
}
</script>

<style scoped>
.converter{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

</style>