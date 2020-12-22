<script>
	// Declaring variables

	// @variable loaded
	// Determines if the component is loaded
	// or no (required for transition to work)
	let loaded = false;
	
	// Importing animations
	import { fade } from "svelte/transition";
	import { onMount } from "svelte";

  // Services List
  let services = [
    // 
    // Entertainment Services
    {
      catId: 0,
      name: "Развлекательные",
      description: "Сервисы, которые всегда смогут Вас повеселить!",

      items: [
        {
          id: 0,
          name: "Pawcapsu",
          color: "black",

          badges: [
            {
              backgroundColor: "black",
              text: "В разработке"
            }
          ],

          description: "Социальная сеть для любителей всего, у чего есть лапки. Огромное количество инструментов и функционала, сделанного под руководством людей специально для людей.",

          href: "https://paws.unfull.ml",
          logotype: "./logotype/pawcapsu/white-full.svg", 
        },
        {
          id: 0,
          name: "Lococovu",
          color: "indigo-400",

          badges: [
            {
              backgroundColor: "black",
              text: "В разработке"
            }
          ],

          description: "Сборник всего самого интересного из мира развлечений, созданных нашим развлекательным подразделением Lococovu Studios специально для Вас. Максимально миниатюрные мини-игры в Майнкрафте, комиксы, визуальные новелы, различные небольшие игры и многое другое именно тут!",

          logotype: "./logotype/lococovu/white-full.svg", 
        },
      ]
    },

    // 
    // Learning Services
    {
      catId: 1,
      name: "Обучающие",
      description: "Ресурсы, которые призваны помочь Вам в обучении. Полностью бесплатные и без рекламы.",

      items: [
        {
          id: 1,
          name: "odzi.dog",
          color: "orange-400",

          badges: [
            {
              backgroundColor: "orange-400",
              text: "В разработке"
            }
          ],

          description: "Полностью бесплатные социальные сервисы для дрессировки и обучению собак. Весь материал сайта создаётся пользователями и проверяется профессионалами своего дела. Множество различных мини-сервисов, которые всегда помогут Вам и Вашему питомцу.",

          href: "https://odzi.dog",
          logotype: "./logotype/odzi/white-full.svg",
        },
        {
          id: 2,
          name: "ctrlpaint.ru",
          color: "blue-400",

          badges: [
            {
              backgroundColor: "blue-400",
              text: "В разработке"
            }
          ],

          description: "Полностью бесплатные уроки по Графическому рисованию. Длина каждого видеоролика не превышает 5-ти минут, в каждом видеоролике подробно рассказывается про каждую методику рисования и про то, как именно их использовать.",

          href: "https://ctrlpaint.ru",
          logotype: "./logotype/ctrlpaint/white-full.svg",
        },
      ]
    },
    {
      catId: "2",
      name: "Для разработчиков",

      status: 0
    }
  ]

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
			<header class="absolute inset-x-0 top-0 w-full py-6 px-8 md:px-6 flex justify-between items-center">
			  <!-- Logotype -->
				<img style="height: 1.2rem;" src="./logotype/black.svg" alt="Black unfull logotype">		

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
			<div class="w-full py-6 px-8 md:px-6 pt-24 md:pt-0">
				<!-- Heading -->
				<div>
					<h1 style="font-family: 'Rubik', sans-serif;" class="text-3xl text-black font-medium">Удобные, небольшие и <span style="font-family: 'Permanent Marker', cursive;" class="text-4xl text-red-400">un</span>нужные сервисы и сайты.</h1>
					<p class="text-extra-xss text-gray-700 mt-1">*unнужные - означает ненужные :)</p>
				</div>

				<!-- Subheading + Button -->
				<div class="mt-12 md:mt-4 w-full relative flex flex-col md:flex-row">
					<!-- Button -->
					<div class="w-full md:w-1/3 md:px-0 md:pr-6">
						<!-- hover:text-black hover:bg-white -->
						<button class="py-3 w-full px-4 opacity-75 cursor-not-allowed bg-black text-white flex items-center justify-center">
							<!-- Text -->
							<p class="text-sm pr-2">Узнать больше</p>

							<!-- Icon -->
							<svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-right"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
						</button>
					</div>

					<!-- Text -->
					<div class="w-full md:px-0 md:w-2/3">
						<p class="text-sm text-gray-700 w-full md:w-2/3">Эта секция всё ещё находится на стадии Раней Разработкий.</p>
					</div>
				</div>
			</div>
		</section>
		
		<!-- Services Panel -->
		<section class="w-full h-auto lg:h-100vh flex flex-col relative">
      <!-- Fast Categories Skip -->
      <div class="w-full py-6 px-6 flex justify-evenly">
        { #each services as category }
          <div on:click={(e) => {
            if (category.status != 0) window.location.href = `#cat${ category.catId }`;
          }} class="{ category.status != 0 ? "cursor-pointer" : "opacity-75 cursor-not-allowed" } mx-2 px-4 py-2 rounded-full bg-gray-300 text-black text-sm">
            { category.name }
          </div>
        { /each }
      </div>

      <div style="overflow: hidden; overflow-y: auto;" class="w-full flex flex-grow relative">
        <div class="lg:absolute w-full h-full px-6 lg:px-12">
          <!-- Services List -->
          { #each services as category }
            { #if category.status != 0 }
              <!-- Category Wapper -->
              <div id="cat{ category.catId }" class="w-full pb-6 pt-2">
                <!-- Title -->
                <h1 class="text-2xl text-black">{ category.name }</h1>
                <p class="text-md text-gray-900">{ category.description }</p>

                <!-- Items -->
                <div class="w-full mt-4 relative">
                  { #each category.items as service }
                  <div class="w-full px-6 py-3 border-1 border-gray-300 bg-{ service.color }">
                      <!-- Logotype -->
                      <div class="w-full flex items-center">
                        <img style="height: 1.5rem;" src="{ service.logotype }" alt="Service Logotype">
                        
                        { #if service.badges != null && service.badges.length > 0 }
                          <!-- Divider -->
                          <div style="height: 1.2rem; width: 1px;" class="bg-white rounded-md ml-2"></div>
                        
                          <!-- Badges -->
                          <div class="flex">
                            { #each service.badges as badge }
                              <div class="mx-1 text-extra-xs px-1 py-1 rounded-full bg-{ badge.color } text-white">
                                { badge.text }
                              </div>
                            { /each }
                          </div>
                        { /if }
                      </div>

                      <!-- Description -->
                      <p class="text-sm my-3 text-white">{ service.description }</p>

                      <!-- Buttons -->
                      <div class="w-full flex">
                        <!-- Goto -->
                        <button on:click={(e) => {
                          if (service.href != null) window.location.href = service.href;
                        }} class="mr-2 py-3 w-full px-4 { service.href != null ? "cursor-pointer" : "cursor-not-allowed opacity-75" } bg-black text-white flex items-center justify-center">
                          <!-- Text -->
                          <p class="text-sm pr-2">Перейти</p>
            
                          <!-- Icon -->
                          <svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-right"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
                        </button>

                        <!-- Support -->
                        <button class="ml-2 py-3 w-full px-4 cursor-not-allowed opacity-75 bg-black text-white flex items-center justify-center">
                          <!-- Icon -->
                          <svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-heart"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
                          
                          <!-- Text -->
                          <p class="text-sm pl-2">Поддержать</p>
                        </button>
                      </div>
                    </div>
                  { /each }
                </div>
              </div>
            { /if }
          { /each }
        </div>
      </div>
		</section>
	</main>
{ /if }