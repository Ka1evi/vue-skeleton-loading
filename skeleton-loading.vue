<template>
	<div class="skeleton-loading">
		<div class="timeline-item" v-if="type === 'basic'">
			<div class="animated-background" v-for="(n, index) of numbers" :key="index" :style="{width: width + 'px'}">
				<div class="background-masker header-top"></div>
				<div class="background-masker header-left"></div>
				<div class="background-masker header-right" :style="{left: width*0.9 + 'px'}"></div>
				<div class="background-masker header-bottom"></div>
				<div class="background-masker subheader-left"></div>
				<div class="background-masker subheader-right" :style="{left: width*0.9 + 'px'}"></div>
				<div class="background-masker subheader-bottom"></div>
			</div>
		</div>
		<div class="timeline-item" v-if="type === 'simple'">
			<div class="animated-background simple" v-for="(n, index) of numbers" :key="index" :style="{width: width + 'px'}">
				<div class="background-masker header-top"></div>
				<div class="background-masker header-left"></div>
				<div class="background-masker header-right" :style="{left: width*0.9-150 + 'px'}"></div>
				<div class="background-masker header-bottom"></div>
				<div class="background-masker subheader-left"></div>
				<div class="background-masker subheader-right" :style="{left: width*0.9 + 'px'}"></div>
				<div class="background-masker subheader-bottom"></div>
				<div class="background-masker subheader-left-second"></div>
				<div class="background-masker subheader-right-second" :style="{left: width*0.9 + 'px'}"></div>
				<div class="background-masker subheader-bottom-second"></div>
				<div class="background-masker subheader-left-third"></div>
				<div class="background-masker subheader-right-third" :style="{left: width*0.9-220 + 'px'}"></div>
			</div>
		</div>
		<div class="timeline-item" v-if="type === 'complex'">
			<div class="animated-background complex" v-for="(n, index) of numbers" :key="index" :style="{width: width + 'px'}">
				<div class="background-masker header-top"></div>
				<div class="background-masker header-left"></div>
				<div class="background-masker header-right" :style="{left: width*0.9 + 'px'}"></div>
				<div class="background-masker header-bottom"></div>
				<div class="background-masker subheader-left"></div>
				<div class="background-masker subheader-right" :style="{left: width*0.9-130 + 'px'}"></div>
				<div class="background-masker subheader-bottom"></div>
				<div class="background-masker content-top"></div>
				<div class="background-masker content-first-end" :style="{left: width*0.9-180 + 'px'}"></div>
				<div class="background-masker content-second-line"></div>
				<div class="background-masker content-second-end" :style="{left: width*0.9-220 + 'px'}"></div>
				<div class="background-masker content-third-line"></div>
				<div class="background-masker content-third-end" :style="{left: width*0.9 + 'px'}"></div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			type: {
				type: String,
				required: false,
				default: 'basic'
			},
			numbers: {
				type: Number,
				required: false,
				default: 1
			},
			width: {
				type: Number,
				required: false,
				default: 600
			}
		}
	}
	
</script>


<style scoped>
	.timeline-item {
	   background: #fff;
	   padding: 12px;
	   margin: 0 auto;
	   /* max-width: 472px; */
	   /* min-height: 200px; */
	}


	@keyframes placeHolderShimmer{
	    0%{
	        background-position: -468px 0
	    }
	    100%{
	        background-position: 468px 0
	    }
	}

	.animated-background {
	    animation-duration: 1s;
	    animation-fill-mode: forwards;
	    animation-iteration-count: infinite;
	    animation-name: placeHolderShimmer;
	    animation-timing-function: linear;
	    background: #f6f7f8;
	    background: linear-gradient(to right, #eeeeee 8%, #dddddd 18%, #eeeeee 33%);
	    background-size: 800px 104px;
	    height: 40px;
	    position: relative;
	    margin-bottom: 18px;
	}

	.simple {
		height: 64px;
	}

	.complex {
		height: 96px;
	}

	.animated-background:last-child {
		margin-bottom: 0px;
	}


	.background-masker {
	    background: #fff;
	    position: absolute;
	}

	/* Every thing below this is just positioning */

	.background-masker.header-top,
	.background-masker.header-bottom,
	.background-masker.subheader-bottom {
	    top: 0;
	    left: 40px;
	    right: 0;
	    height: 10px;
	}

	.simple .background-masker.header-top,
	.simple .background-masker.header-bottom,
	.simple .background-masker.subheader-bottom,
	.simple .background-masker.subheader-bottom-second {
	    top: 8px;
	    left: 0px;
	    right: 0;
	    height: 8px;
	}



	.background-masker.header-left,
	.background-masker.subheader-left,
	.background-masker.header-right,
	.background-masker.subheader-right {
	    top: 10px;
	    left: 40px;
	    height: 8px;
	    width: 10px;
	}

	.simple	.background-masker.header-left,
	.simple	.background-masker.subheader-left,
	.simple	.background-masker.header-right,
	.simple	.background-masker.subheader-right,
	.simple	.background-masker.subheader-left-second,
	.simple	.background-masker.subheader-right-second,
	.simple	.background-masker.subheader-left-third,
	.simple	.background-masker.subheader-right-third {
	    top: 0px;
	    left: 0px;
	    height: 8px;
	    width: 10px;
	}

	.background-masker.header-bottom {
	    top: 18px;
	    height: 6px;
	}

	.simple	.background-masker.header-bottom {
	    top: 24px;
	    height: 8px;
	}

	.background-masker.subheader-left,
	.background-masker.subheader-right {
	    top: 24px;
	    height: 6px;
	}

	.simple	.background-masker.subheader-left,
	.simple	.background-masker.subheader-right {
	    top: 16px;
	    height: 8px;
	}


	.background-masker.header-right,
	.background-masker.subheader-right {
	    width: auto;
	    left: 300px;
	    right: 0;
	}

	.simple	.background-masker.header-right,
	.simple	.background-masker.subheader-right,
	.simple	.background-masker.subheader-right-second,
	.simple	.background-masker.subheader-right-third {
	    width: auto;
	    left: 150px;
	    right: 0;
	}

	.background-masker.subheader-right {
	    left: 230px;
	}

	.simple	.background-masker.subheader-right,
	.simple	.background-masker.subheader-right-second {
	    left: 300px;
	}

	.background-masker.subheader-bottom {
	    top: 30px;
	    height: 10px;
	}

	.simple .background-masker.subheader-bottom,
	.simple .background-masker.subheader-bottom-second {
	    top: 40px;
	    height: 8px;
	}

	.simple .background-masker.subheader-left-second,
	.simple .background-masker.subheader-right-second{
		top: 32px;
		height: 8px;
	}
	.simple .background-masker.subheader-bottom-second {
		top: 56px;
	}
	.simple .background-masker.subheader-left-third,
	.simple .background-masker.subheader-right-third  {
	    top: 48px;
	    height: 8px;
	}
	.simple .background-masker.subheader-right-third {
	    left: 220px;
	}

	.background-masker.content-top,
	.background-masker.content-second-line,
	.background-masker.content-third-line,
	.background-masker.content-second-end,
	.background-masker.content-third-end,
	.background-masker.content-first-end {
	    top: 40px;
	    left: 0;
	    right: 0;
	    height: 6px;
	}

	.background-masker.content-top {
	    height:20px;
	}

	.background-masker.content-first-end,
	.background-masker.content-second-end,
	.background-masker.content-third-end{
	    width: auto;
	    left: 380px;
	    right: 0;
	    top: 60px;
	    height: 8px;
	}

	.background-masker.content-second-line  {
	    top: 68px;
	}

	.background-masker.content-second-end {
	    left: 420px;
	    top: 74px;
	}

	.background-masker.content-third-line {
	    top: 82px;
	}

	.background-masker.content-third-end {
	    left: 300px;
	    top: 88px;
	}
</style>