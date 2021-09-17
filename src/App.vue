<template>
	<main>
		<div class="main">
			<div class="intro">
				<figure><img src="./assets/images/image-jeremy.png" alt="profile"></figure>
				<h1>
					<span>Report for<br></span>Jeremy Robsom
				</h1>
			</div>
			<div class="periods">
				<p @click="period = 'daily'" :class="{active : period==='daily'}">Daily</p>
				<p @click="period = 'weekly'" :class="{active : period==='weekly'}">Weekly</p>
				<p @click="period = 'monthly'" :class="{active : period==='monthly'}">Monthly</p>
			</div>
		</div>
		<Section v-for="stat in stats" :key="stat.title" :data="stat" :period="period"/>
	</main>
</template>

<script>
import Section from "./components/Section.vue"

export default {
	name: 'App',
	components: {Section},
	data(){
		return{
			stats: [],
			period: "weekly"
		}
	},
	mounted(){
		fetch("/data.json")
		.then(res => res.json())
		.then(res => this.stats = res)
	}

}
</script>

