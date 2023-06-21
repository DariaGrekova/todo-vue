<template>
  <v-form>
    <v-text-field v-model="newItemTitle"
                  label="Введите название задачи"
                  @keydown.enter.prevent="addTodo"
                  autofocus
                  :rules="[rules.minLength]"
                  required
                  >
    </v-text-field>
  </v-form>
</template>

<script>
const MIN_LENGTH_VALIDATION = 3

export default {
  name: 'InputField',
  data () {
    return {
      newItemTitle: '',
      rules: {
        minLength: value => {
          return (value.length >= MIN_LENGTH_VALIDATION) || `Введите не менее ${MIN_LENGTH_VALIDATION}-х символов.`
        }
      }
    }
  },
  methods: {
    addTodo () {
      if (this.newItemTitle.length >= MIN_LENGTH_VALIDATION) {
        this.$store.dispatch('addTodo', this.newItemTitle)
        this.newItemTitle = ''
      }
    }
  }
}
</script>
