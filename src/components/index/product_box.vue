<template>
	<ul :class="`content${template}`">
		<li v-for="(item,i) in data" :key="i">
			<router-link :to="`/product/${item.id}`">
				<div class="img-box">
					<div :style="`background-image: url(${item.avatar})`"></div>
				</div>
				<div class="text-box">
					<messageBox :textData="{name:item.name,title:item.title,price:item.price}"/>
				</div>
			</router-link>
		</li>
	</ul>
</template>

<script type="text/ecmascript-6">
        import messageBox from '../public/product_message';

        export default {
                components: {messageBox},
                props: ['data', 'template']
        };
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
	.content1
		display flex
		padding-left 0.2rem

		li
			a
				display inline-block
				width 2.5rem
				margin-right 0.2rem

			& .img-box
				width 2.5rem
				height 2.5rem
				border 0.01rem solid rgba(0, 0, 0, 0.1)
				border-radius 0.1rem
				margin-bottom 0.1rem

				div
					width 100%
					height 100%
					background-repeat no-repeat
					background-position center
					background-size 100%

			& .text-box
				width 100%
				padding 0 0.2rem

	.content2
		display flex
		flex-wrap wrap
		padding 0.2rem 0.2rem
		justify-content space-between

		li
			width 48.5%
			margin-top  0.2rem

			.img-box
				div
					width 100%
					padding-top 100%
					background-position center
					background-repeat no-repeat
					background-size 80%
					border-radius 0.1rem
					border 0.01rem solid rgba(100,100,100,0.15)

			.text-box
				margin-top 0.1rem
				padding 0 0.2rem
	.content3
		li
			padding 0.1rem 0.1rem 0.1rem 0.3rem
			border-bottom 0.01rem solid rgba(0, 0, 0, 0.1)

			a
				display flex
				justify-content space-between

				.img-box
					width 35%
					text-align center

					div
						width 100%
						padding-top 100%
						background-position center
						background-repeat no-repeat
						background-size 100%

				.text-box
					width 55%
					display flex
					align-items center
</style>