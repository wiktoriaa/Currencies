<template>
    <table class="table table-striped">     
        <thead> 
            <tr>
                <th>Nazwa waluty</th>
                <th>Kod waluty</th>
                <th>Obecny kurs</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="rate in rates" :key="rate.currency">
                <td>{{ rate.currency }}</td>
                <td>{{ rate.code }}</td>
                <td>{{ rate.mid }}</td>
            </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        props: {
            rates: Array
        }
    }
</script>
