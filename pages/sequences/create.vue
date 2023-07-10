<template>
<b-row align-h="center">
  <b-col cols="8">
    <b-card>
      <b-card-body>
        <b-form @submit.prevent="createChain">
        <b-form-group label="Chain" label-for="text-chain" description='Character letters can only be: A,
T, C, G; "ACTTAACGGCGGGGCTATA"'>
      <b-form-input type="text" id="text-chain" v-model="chain"></b-form-input>
    </b-form-group>
    <b-button type="submit" variant="success">Create sequences</b-button>
  </b-form>
      </b-card-body>
    </b-card>
  </b-col>
  </b-row>
</template>

<script>
export default {
  data() {
    return {
      chain: '',
    };
  },
  methods: {
    async createChain() {
      const data = {
        chain: this.chain,
      };
      try {
        const response = await this.$axios.post('/sequences',data)
        this.$bvToast.toast(response.data.chain, {
          title: 'Sequence created',
          variant: 'success',
          autoHideDelay: 5000,
        });

        setTimeout(() => {
          this.$router.push({name: 'sequences-total'})
        }, 1500)

      } catch (error) {
        this.$bvToast.toast('Error', {
          title: 'Something went wrong',
          variant: 'danger',
          autoHideDelay: 5000,
        });
      }
    },
  },
};
</script>
