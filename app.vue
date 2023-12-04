<template>
	<NuxtLayout>
		<v-app>
			<header>
				<v-app-bar app>
					<v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
					<v-toolbar-title><NuxtLink to="/">ダリアリオ合同会社 (Dahliario, LLC)</NuxtLink></v-toolbar-title>
				</v-app-bar>
				<v-navigation-drawer
					v-model="drawer"
					mobile-breakpoint="sm"
					temporary
				>
					<v-list
						nav
						dense
					>
						<v-list-item v-for="(menuItem, index) in menuItems" :key="index">
							<v-list-item-title><v-btn :href="menuItem.url">{{ menuItem.name }}</v-btn></v-list-item-title>
						</v-list-item>
					</v-list>
				</v-navigation-drawer>
			</header>
			<v-main>
				<NuxtPage />
			</v-main>
			<v-footer app>
				Copyright &copy; Dahliario, LLC. All rights reserved.
			</v-footer>
		</v-app>
	</NuxtLayout>
</template>

<script lang=ts>
//import HelloWorld from "./components/HelloWorld";

export default {
	name: "App",
	data(){
		return {
			drawer: false,
			menuItems: [
				{
					name: '会社概要',
					url: '/about',
				},
				{
					name: '事業内容',
					url: '/projects',
				},
				{
					name: 'お問い合わせ',
					url: '/contact',
				},
			],
		}
	},
};
</script>

