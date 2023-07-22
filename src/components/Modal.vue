<template>
    <div 
        class="modal-container" 
        id="m3-o" 
        style="--m-background: var(--global-background);">
        <div class="modal" style="--m-shadow: 0 0 10rem 0">
            <h1 class="modal__title">{{ text }}</h1>
            <i class="fa-solid fa-check link-2" v-if="isAdded === 'true'"></i>
            <i class="fa-solid fa-trash link-2" v-if="isDeleted === 'true'"></i>
        </div>
    </div>
</template>

<script setup>
    defineProps({
        text: String,
        isAdded: String,
        isDeleted: String
    })
</script>

<style scoped>
.modal-container {
	position: fixed;
	top: 88%;
	left: 85%;
	z-index: 10;
  
	justify-content: center;
	align-items: center;
  
	width: 70%;
	height: 100%;
  
  }
  
  .modal-container:target {
	display: flex;
  }
  
  .modal {
	width: 20%;
	padding: 1rem 1rem;
	border-radius: .8rem;
  
	color: var(--lightModal);
	background: var(--background);
	box-shadow: var(--m-shadow, .4rem .4rem 10.2rem .2rem) var(--shadow-1);
	position: relative;
  
	overflow: hidden;
  }
  
  .modal__title {
	font-size: 1rem;
  }

  .link-2 {
	width: 1rem;
	height: 0.5rem;

  
	color: inherit;
	font-size: 1.3rem;
  
	position: absolute;
	top: 1.3rem;
	right: 1rem;
  
	display: flex;
	justify-content: center;
	align-items: center;
  
	transition: .2s;
  }

  @media only screen and (max-width: 1550px) {
	.modal-container {
		left: 79%;
		width: 100%;
	}

	.modal__title {
		font-size: 0.9rem;
		margin-right: 1rem;
  }
  }

  @media only screen and (max-width: 850px) {
	.modal-container {
		left: 49%;
		width: 250%;
	}

	.modal__title {
		font-size: 0.9rem;
		margin-right: 1rem;
  }
  }
  
</style>