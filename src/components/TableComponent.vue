<template>
  <table>
    <thead>
      <tr>
        <th>Team</th>
        <th>Points</th>
        <th>GD</th>
        <th>GA</th>
      </tr>
    </thead>
    <tbody>
      <tr :key="index" v-for="(team, index) in teams">
        <td>
          <figure class="image"><img :src="team.crestURI" :alt="team.teamName" ></figure>
          {{team.teamName}}
        </td>
        <td>{{team.points}}</td>
        <td>{{team.goalDifferenc}}</td>
        <td>{{team.goalsAgainst}}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "TableComponent",
  data(){
    return{
      items: [
        {
          name: "Liverpool F.C",
        },
        {
          name: "Arsenal F.C",
        },
        {
          name: "Chelsea F.C",
        },
        {
          name: "Manchester United"
        }
      ]
    }
  },
  props: {
    teams: {
      type: Array
    }
  }
}
</script>

<style lang="css">
.image{
  display: inline-block;
  flex-shrink: 0;
  height: 20px;
  text-align: center;
  vertical-align: top;
  width: 20px
}
</style>
