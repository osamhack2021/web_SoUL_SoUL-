<template>
	<div>
		<!-- <Header /> -->
		<div id="main-contaniner">
			<section id="writing-box-header">
				<button id="button-poem" @click="changeBtn(1)" :class="{ gray: btn == 1}" class="button-default button-clicked">시</button>
				<button id="button-prose" @click="changeBtn(2)" :class="{ gray: btn == 2}" class="button-default">산문</button>
				<button id="button-novel" @click="changeBtn(3)" :class="{ gray: btn == 3}" class="button-default">소설</button>
			</section>
			<section id="writing-box">
				<input type="text" id="munhakTitle" placeholder="제목"/>
				<textarea id="maintext-box" v-model="textValue" cols="85" rows="25" autofocus placeholder="본문" />
				<div id="date-box">{{Today}}</div>
			</section>
			<section id="writing-box-footer">
				<div id="public-checkbox" class="form-check form-switch">
					<input class="form-check-input" type="checkbox" id="public">
					<label class="form-check-label" for="public">공개 여부</label>
				</div>
				<button id="button-submit" :disabled="textValue == ''">업로드</button>
			</section>
		</div>
	</div>
</template>

<script>
	// import Header from '../components/Header'
	import dayjs from "dayjs"
	
	export default {
		// components: {Header, },
		data() {
			return {
				btn: 1,
				Today: dayjs().format("YYYY-MM-DD"),
				textValue: "",
			};
		}, 
		methods: {
			// resize(obj) {
			// 	obj.style.height = "1px";
			// 	obj.style.height = (12 + obj.scrollHeight) + "px";
			// }
			changeBtn(n){
				this.btn = n;
			}
	}
		// computed: {
		// 	user() {
		// 		return this.$store.state.user;
		// 	}
		// }
	}
</script>

<style>
	button:focus { outline: none;}
</style>

<style scoped>	
	#main-contaniner #writing-box-header {
		width: 42.5rem;
		display: flex;
		justify-content: center;
		align-items: center;
		margin: 0 auto 16px;
	}
	#writing-box #munhakTitle {
		width: 60%;
		margin: 16px auto 10px;
		/* border-bottom: 2px solid #C4C4C4; border-right: 0; border-left: 0; border-top: 0; */
		border: 0;
		text-align: center;
		font-size: 22px;
	}
	#main-contaniner #writing-box-header .button-default {
		width: 100px;
		height: 40px;
		border: 2px solid #C4C4C4;
		border-radius: 10px;
		margin: 0 30px;
		color: gray;
	}
	.gray {
		background-color: #C4C4C4;
		color: white !important;
	}
</style>

