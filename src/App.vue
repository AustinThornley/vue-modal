<template>
  <h1>{{ title }}</h1>
	<p>Open modal below</p>
	<div v-if="showModal">
  	<Modal :header="header" :text="text" theme="sale" @close="toggleModal"/>
	</div>
	<button @click.alt="toggleModal">Open Modal (alt)</button>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App!! :)',
			header: 'Enter the giveaway now!',
			text: 'Win any vinyl of your choice!',
			showModal: false
    };
  },
	methods: {
		toggleModal() {
			this.showModal = !this.showModal;
		}
	}
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid;
  display: inline-block;
  padding-bottom: 10px;
}
</style>