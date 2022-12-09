<template>
  <div>
    <h1>{{ coin.name }} Detail Page</h1>
    <table border="1 px solid">
      <thead>
        <th>Symbol</th>
        <th>Rank</th>
        <th>Price - US $</th>
        <th>Market Cap - US $</th>
      </thead>
      <tr>
        <td>{{ coin.symbol }}</td>
        <td>{{ coin.rank }}</td>
        <td>{{ coin.price_usd }}</td>
        <td>{{ coin.market_cap_usd }}</td>
      </tr>
    </table>
  </div>
</template>

<script setup>
const route = useRoute();
const { data } = await useFetch("/api/ticker?id=" + route.params.id);
const coin = data.value[0];
</script>

<style lang="scss" scoped></style>
