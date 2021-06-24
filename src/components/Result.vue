<template>
	<div class="result">
		<div class="title">{{ results[resultIndex].title }}</div>
		<div class="desc">
			{{ results[resultIndex].desc }}
		</div>
	</div>
</template>

<script>
export default {
	props: ["results", "totalCorrect"],
	computed: {
		resultIndex() {
			let index = 0;

			this.results.forEach((e, i) => {
				// checks if the total number of correct answers is above the minimun and bellow the maximum
				if (e.min <= this.totalCorrect && e.max >= this.totalCorrect) {
					// i represents the current index in the loop
					index = i;
				}
			});
			return index;
		},
	},
};
</script>
