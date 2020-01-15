<template>
  <div class="row">
    <form action="">
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <label for="newQuote">Quote</label>
        <textarea
          name="newQuote"
          id="newQuote"
          rows="3"
          class="form-control"
          v-model="quote"
          :disabled="quoteCount === maxQuotes"
        ></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <button class="btn btn-primary" @click.prevent="createNew" :disabled="!this.quote">Add quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  props: ['quoteCount', 'maxQuotes'],
  data() {
    return {
      quote: ''
    }
  },
  methods: {
    createNew() {
      this.$emit('quoteAdded', this.quote)
      this.quote = ''
    }
  }
}
</script>

<style></style>
