<script>
	// Declaring variables

	// @variable loaded
	// Determines if the component is loaded
	// or no (required for transition to work)
	let loaded = false;
	
	// Importing animations
	import { fade } from "svelte/transition";
	import { onMount } from "svelte";

	// Let's now change our loaded state on component mount.
	onMount(() => {
		setTimeout(() => {
			loaded = true;
		}, 25)
	});
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Rubik:wght@500&display=swap');
</style>

{ #if loaded }
	<main in:fade class="bg-gray-100 w-full lg:h-100vh relative flex flex-col lg:flex-row items-center justify-center">
		<!-- Text Panel -->
		<section class="w-full h-full relative flex flex-col lg:flex-row items-end">
			<!-- Header -->
			<header class="absolute inset-x-0 top-0 w-full py-6 px-8 md:px-6 flex justify-between">
			  <!-- Logotype -->
				<img style="height: 1.1rem;" src="./logotype/black.svg" alt="Black unfull logotype">		

				<!-- Some Buttons -->
				<button class="text-black px-4 py-2 hover:text-white hover:bg-black flex items-center">
					<!-- Icon -->
					<svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-external-link"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>

					<!-- Text -->
					<p class="text-sm ml-2">
						Связаться
					</p>
				</button>
			</header>

			<!-- Text -->
			<div class="w-full py-6 px-12 md:px-6 pt-24 md:pt-0">
				<!-- Heading -->
				<div>
					<h1 style="font-family: 'Rubik', sans-serif;" class="text-4xl text-black font-medium">Удобные, небольшие и <span style="font-family: 'Permanent Marker', cursive;" class="text-4xl text-red-400">un</span>нужные сервисы и сайты.</h1>
					<p class="text-extra-xss text-gray-700 mt-1">*unнужные - означает ненужные :)</p>
				</div>

				<!-- Subheading + Button -->
				<div class="mt-12 md:mt-4 w-full relative flex flex-col md:flex-row">
					<!-- Button -->
					<div class="w-full md:w-1/3 px-12 md:px-0 md:pr-6">
						<!-- hover:text-black hover:bg-white -->
						<button class="py-3 w-full px-4 opacity-75 cursor-not-allowed bg-black text-white flex items-center justify-center">
							<!-- Text -->
							<p class="text-sm pr-2">Узнать больше</p>

							<!-- Icon -->
							<svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-right"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
						</button>
					</div>

					<!-- Text -->
					<div class="w-full px-12 md:px-0 md:w-2/3">
						<p class="text-sm text-gray-700 w-full md:w-2/3">Эта секция всё ещё находится на стадии Раней Разработкий.</p>
					</div>
				</div>
			</div>
		</section>
		
		<!-- Images && Services Panel -->
		<section class="w-full h-100vh flex justify-center items-center">
			<!-- Mobile view -->
			<div class="w-full h-full relative lg:hidden">
				<!-- 
					@service ctrl+paint
				 -->
				<div class="w-full relative">
					<div style="padding-top: 100%;" class="bg-indigo-400 relative">
						<div on:click={(e) => {
							window.location.href = "https://ctrlpaint.ru";
						}} class="absolute inset-0 w-full h-full cursor-pointer px-2 py-2 flex flex-col justify-center items-center">
							<!-- Some Texts -->
							<div class="w-full text-center px-6">
								<h1 class="text-2xl text-white">Художникам</h1>

								<p class="text-white text-base">Перевод профессиональных и <span class="border-b-1 border-dotted border-white">полностью бесплатных</span>, 5-ти минутных и понятных уроков по графическому рисованию.</p>
							</div>

							<!-- Logotype -->
							<div class="w-full flex justify-center mt-6">
								<img style="height: 2.5rem;" src="./logotype/ctrlpaint/white-full.svg" alt="Ctrl+Paint Logotype">
							</div>
						</div>
					</div>
				</div>

				<!-- 
					@service Paw Universes
				 -->
				<div class="w-full relative">
					<div style="padding-top: 100%;" class="bg-black relative">
						<!-- Locked Sign -->
						<div style="z-index: 2; background: rgba(0,0,0,0.8);" class="absolute cursor-not-allowed inset-0 w-full h-full">
							<div class="w-full h-full flex flex-col justify-center items-center">
								<img style="height: 3rem; width: 3rem;" src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/120/apple/237/lock_1f512.png" alt="Locked Emoji from emojipedia cdn">

								<!-- Text -->
								<div class="text-center px-4 relative">
									<h1 class="mt-4 text-xl text-white font-semibold">Разработка</h1>
									<p class="text-base text-gray-100">Этот сервис находится в стадии глубочайшей разработки.</p>
								</div>
							</div>							
						</div>

						<div on:click={() => {
							window.location.href = "https://paw.unfull.ml/";
						}} class="cursor-pointer absolute inset-0 w-full h-full px-3 py-3 flex flex-col justify-center items-center">
							<!-- Some Texts -->
							<div class="w-full text-center px-6">
								<h1 class="text-2xl text-white">Лапколюбителям</h1>

								<p class="text-white text-base">Социальная сеть для любителей <span class="border-b-1 border-dotted border-white">Щенячьего Патруля</span>, <span class="border-b-1 border-dotted border-white">Улицы 101-го Далматинца</span> и т.п.</p>
							</div>

							<!-- Logotype -->
							<div class="w-full flex justify-center mt-6">
								<img style="height: 2.5rem;" src="./logotype/paw/white-full.svg" alt="Paw Universes Logotype">
							</div>
						</div>
					</div>
				</div>

				<!-- 
					@service odzi
				 -->
				<div class="w-full relative">
					<div style="padding-top: 100%;" class="bg-yellow-500 relative">
						<!-- Locked Sign -->
						<div style="z-index: 2; background: rgba(0,0,0,0.8);" class="absolute cursor-not-allowed inset-0 w-full h-full">
							<div class="w-full h-full flex flex-col justify-center items-center">
								<img style="height: 2rem; width: 2rem;" src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/120/apple/237/lock_1f512.png" alt="Locked Emoji from emojipedia cdn">

								<!-- Text -->
								<div class="text-center px-4">
									<h1 class="mt-4 text-xl text-white font-semibold">Разработка</h1>
									<p class="text-base text-gray-100">Этот сервис находится в стадии глубочайшей разработки.</p>
								</div>
							</div>							
						</div>
						
						<div style="z-index: 1;" class="cursor-not-allowed absolute inset-0 w-full h-full px-3 py-3 flex flex-col justify-center items-center">
							<!-- Some Texts -->
							<div class="w-full text-center px-6">
								<h1 class="text-2xl text-white">Собачникам</h1>

								<p class="text-white text-base">Полностью <span class="border-b-1 border-dotted border-white">бесплатные</span> социальные сервисы для дрессировки и обучению собак.</p>
							</div>

							<!-- Logotype -->
							<div class="w-full flex justify-center mt-6">
								<img style="height: 2.5rem;" src="./logotype/odzi/white-full.svg" alt="Odzi Logotype">
							</div>
						</div>
					</div>
				</div>
			</div>

			<!-- Desktop view -->
			<div class="w-full h-full hidden lg:block relative">
				<!-- Row #1 -->
				<div class="w-full flex">
					<div class="w-1/3">
						<div style="padding-top: 100%; border-top-right-radius: 50%;" class="bg-yellow-300"></div>
					</div>

					<div class="w-1/3">
						<div style="padding-top: 100%; border-bottom-right-radius: 50%;" class="bg-pink-300"></div>
					</div>

					<!-- 
						@service Paw Universes
					 -->
					<div class="w-1/3 relative">
						<div style="padding-top: 100%; border-top-left-radius: 50%;" class="bg-black relative">
							<!-- Locked Sign -->
							<div style="z-index: 2; background: rgba(0,0,0,0.8); border-top-left-radius: 50%;" class="absolute cursor-not-allowed inset-0 w-full h-full">
								<div class="w-full h-full flex flex-col justify-center items-center">
									<img style="height: 2rem; width: 2rem;" src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/120/apple/237/lock_1f512.png" alt="Locked Emoji from emojipedia cdn">

									<!-- Text -->
									<div class="text-center px-4 relative">
										<h1 class="mt-4 text-md text-white font-semibold">Разработка</h1>
										<p class="text-sm text-gray-100">Этот сервис находится в стадии глубочайшей разработки.</p>
									</div>
								</div>							
							</div>

							<div on:click={() => {
								window.location.href = "https://paw.unfull.ml/";
							}} class="cursor-pointer absolute inset-0 w-full h-full px-3 py-3 flex flex-col justify-end items-end">
								<!-- Some Texts -->
								<div class="w-full text-right">
									<h1 class="text-xl text-white">Лапколюбителям</h1>

									<p class="text-white text-xs">Социальная сеть для любителей <span class="border-b-1 border-dotted border-white">Щенячьего Патруля</span>, <span class="border-b-1 border-dotted border-white">Улицы 101-го Далматинца</span> и т.п.</p>
								</div>

								<!-- Logotype -->
								<div class="w-full flex items-center mt-4">
									<img style="height: 1.5rem;" src="./logotype/paw/white-full.svg" alt="Paw Universes Logotype">
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Row #2 -->
				<div class="w-full flex">
					<!-- 
						@service ctrlpaint.ru
					 -->
					<div class="w-1/3 relative">
						<div style="padding-top: 100%;" class="bg-indigo-400 relative">
							<div on:click={(e) => {
								window.location.href = "https://ctrlpaint.ru";
							}} class="absolute inset-0 w-full h-full cursor-pointer px-2 py-2 flex flex-col justify-end items-end">
								<!-- Some Texts -->
								<div>
									<h1 class="text-xl text-white">Художникам</h1>

									<p class="text-white text-xs">Перевод профессиональных и <span class="border-b-1 border-dotted border-white">полностью бесплатных</span>, 5-ти минутных и понятных уроков по графическому рисованию.</p>
								</div>

								<!-- Logotype -->
								<div class="w-full flex items-center mt-4">
									<img style="height: 1.5rem;" src="./logotype/ctrlpaint/white-full.svg" alt="Ctrl+Paint Logotype">
								</div>
							</div>
						</div>
					</div>

					<div class="w-1/3">
						<!-- https://source.unsplash.com/random/900x900 -->
						<div style="padding-top: 100%; border-radius: 50%; background-image: url('https://source.unsplash.com/random/900x900'); background-size: cover; background-repeat: no-repeat;" class="bg-black"></div>
					</div>

					<!-- 
						@service odzi
					 -->
					<div class="w-1/3">
						<div style="padding-top: 100%; border-bottom-right-radius: 50%;" class="bg-yellow-500 relative">
							<!-- Locked Sign -->
							<div style="z-index: 2; background: rgba(0,0,0,0.8); border-bottom-right-radius: 50%;" class="absolute cursor-not-allowed inset-0 w-full h-full">
								<div class="w-full h-full flex flex-col justify-center items-center">
									<img style="height: 2rem; width: 2rem;" src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/120/apple/237/lock_1f512.png" alt="Locked Emoji from emojipedia cdn">

									<!-- Text -->
									<div class="text-center px-4">
										<h1 class="mt-4 text-md text-white font-semibold">Разработка</h1>
										<p class="text-sm text-gray-100">Этот сервис находится в стадии глубочайшей разработки.</p>
									</div>
								</div>							
							</div>
							
							<div style="z-index: 1;" class="cursor-not-allowed absolute inset-0 w-full h-full px-3 py-3 flex flex-col justify-end items-end">
								<!-- Some Texts -->
								<div class="w-full text-left">
									<h1 class="text-xl text-white">Собачникам</h1>

									<p class="text-white text-xs">Полностью <span class="border-b-1 border-dotted border-white">бесплатные</span> социальные сервисы для дрессировки и обучению собак.</p>
								</div>

								<!-- Logotype -->
								<div class="w-full flex items-center mt-4">
									<img style="height: 1.5rem;" src="./logotype/odzi/white-full.svg" alt="Odzi Logotype">
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Row #3 -->
				<div class="w-full flex">
					<div class="w-1/3">
						<div style="padding-top: 100%;" class="bg-pink-300"></div>
					</div>

					<div class="w-1/3">
						<div style="padding-top: 100%;" class="bg-yellow-300"></div>
					</div>

					<div class="w-1/3">
						<div style="padding-top: 100%; border-top-right-radius: 50%; border-bottom-left-radius: 50%;" class="bg-pink-300"></div>
					</div>
				</div>
			</div>
		</section>
		<!-- Coming soon Screen
		<div class="flex flex-col items-center">
			Logotype
			<div>
				<img style="height: 1.2rem;" src="./logotype/black.svg" alt="Black unfull logotype">		
			</div>

			Texts
			<div class="text-center w-2/3 mt-8">
				Big Title
				<h1 class="text-xl text-black">New, small and <span style="font-family: 'Permanent Marker', cursive;" class="text-base text-red-400">un</span>wanted websites and services</h1>
			</div>

			Button
			<div class="mt-12 text-center">
				<button class="opacity-75 cursor-not-allowed px-4 py-1 bg-black text-white rounded-md text-sm">
					Subscribe to updates
				</button>
				
				
				<p class="text-xs text-gray-800 mt-1">Coming soon</p>
			</div>
		</div> -->
	</main>
{ /if }