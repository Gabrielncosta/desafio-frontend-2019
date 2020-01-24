<template>
      <tr>
        <th scope="row">
          <Garbage class="icon"/>
         </th>
        <td>
          <p class="purple bold">Eletrônicos</p>
          <p class="bold">{{ list.name }}</p>
        </td>
        <td></td>
        <td>{{ list.price }}</td>
        <td>@mdo</td>
      </tr>
</template>

<script>
  import Garbage from '../assets/svg/garbage.svg';

  export default {
    name: 'Table',
    props: ['list'],
    components: {
      Garbage,
    },
  }
     
</script>


<style lang="scss" scoped>
  .icon {
    fill: #cfcfcf;
   
  }

</style>
