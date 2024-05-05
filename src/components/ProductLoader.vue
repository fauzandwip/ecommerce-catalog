<script setup></script>
<template>
	<div id="loader">
		<div class="loader"></div>
	</div>
</template>

<style scoped>
#loader {
	background-color: var(--c-white);
	width: 100%;
	max-height: 100%;
	border-color: black;
	box-shadow: 2px 4px 21px 0 var(--color-shadow);
	border-radius: 10px;
	display: flex;
	justify-content: center;
	align-items: center;
}

.loader {
	border: 16px solid #f3f3f3;
	border-radius: 50%;
	border-top: 16px solid #3498db;
	width: 120px;
	height: 120px;
	-webkit-animation: spin 2s linear infinite; /* Safari */
	animation: spin 2s linear infinite;
}

/* Safari */
@-webkit-keyframes spin {
	0% {
		-webkit-transform: rotate(0deg);
	}
	100% {
		-webkit-transform: rotate(360deg);
	}
}

@keyframes spin {
	0% {
		transform: rotate(0deg);
	}
	100% {
		transform: rotate(360deg);
	}
}
</style>
