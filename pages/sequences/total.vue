<template>
  <b-card title="Count sequences">
  <b-card-text>
    <p class="h2">There are <b-badge>{{ data.count_sequence_string }}</b-badge> sequences</p>
    <p class="h2">There are
       <b-badge>{{ data.count_no_sequence_string }}</b-badge> no sequences</p>
  </b-card-text>
  <b-button @click="getTotal" href="#" variant="primary">Calculate sequences</b-button>
</b-card>
</template>


<script>
export default {
  data() {
    return {
      data: {
        count_sequence_string: 0,
        count_no_sequence_string: 0
      },
    };
  },
  methods: {
    getTotal() {
      this.$axios.get('/sequences-total')
        .then((response) => {
          this.data.count_no_sequence_string = response.data.count_no_sequence_string
          this.data.count_sequence_string = response.data.count_sequence_string

        })
        .catch((error) => {
          console.error('Error:', error);
        });
    },
  },
};
</script>
