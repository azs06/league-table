<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
<button class="button" type="button" name="button">Click Here</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>
