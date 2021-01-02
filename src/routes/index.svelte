<script>
	// Declaring variables

	// @variable loaded
	// Determines if the component is loaded
	// or no (required for transition to work)
	let loaded = false;
	
	// Importing animations
	import { fade, slide } from "svelte/transition";
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
          color: "yellow-400",

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
  ];

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
	<main in:fade class="relative">
    <div class="bg-gray-200 w-full relative flex">
      <!-- Text Panel -->
      <section class="w-full h-screen relative flex flex-col lg:flex-row items-end">
        <!-- Header -->
        <header class="absolute inset-x-0 top-0 w-full py-6 px-8 md:px-6 flex justify-between items-center">
          <!-- Logotype -->
          <img style="height: 1.2rem;" src="./logotype/black.svg" alt="Black unfull logotype">		
        
          <!-- Some Links -->
          <div class="flex items-center">
            <a class="mx-3 text-xs text-gray-900 opacity-75 transition duration-200 ease-in-out hover:text-black hover:opacity-100" href="/">Сервисы</a>
            <a class="mx-3 text-xs text-gray-900 opacity-75 transition duration-200 ease-in-out hover:text-black hover:opacity-100" href="/">Поддержка</a>
            <a class="mx-3 text-xs text-gray-900 opacity-75 transition duration-200 ease-in-out hover:text-black hover:opacity-100" href="/">Наши цели</a>
            <a class="mx-2 text-xs text-gray-900 opacity-75 transition duration-200 ease-in-out hover:text-black hover:opacity-100" href="/">Про нас</a>
          </div>
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
            <div class="w-full flex md:px-0 md:pr-6">
              <button on:click={(e) => {
                window.location.href = "#services";
              }} class="mr-2 py-3 w-full px-4 cursor-pointer bg-black text-white flex items-center justify-center">
                <!-- Text -->
                <p class="text-sm pr-2">Cписок сервисов</p>

                <!-- Icon -->
                <svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-right"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
              </button>

              <button class="w-full text-black ml-2 px-4 py-3 hover:text-white hover:bg-black flex justify-center items-center">
                <!-- Icon -->
                <svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-external-link"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
    
                <!-- Text -->
                <p class="text-sm ml-2">
                  Связаться
                </p>
              </button>
            </div>
          </div>
        </div>
      </section>
      
      <!-- Illustrations Panel -->
      <section style="z-index: 1;" class="w-full h-auto lg:h-100vh hidden lg:flex justify-center items-end relative">
        <!-- Background #1 -->
        <div in:slide={{ duration: 850 }} style="height: 40vh;" class="opacity-75 absolute bottom-0 left-0 w-2/3 shadow-xl bg-white rounded-t-lg">
          <!-- Badge -->
          <div class="w-full flex justify-center py-3">
            <div class="opacity-75 text-sm px-3 py-1 rounded-full bg-gray-100">
              Преимущество 3/3
            </div>
          </div>

          <!-- Feature Title -->
          <h1 class="text-xl text-center font-bold">Курируется сообществом</h1>
        </div>
        
        <!-- Main Features Screen -->
        <div in:slide={{ duration: 1000 }} style="height: 65vh; z-index: 2;" class="w-2/3 shadow-xl bg-white rounded-t-lg relative">
          <!-- Badge -->
          <div class="w-full flex justify-center py-3">
            <div class="opacity-75 text-sm px-3 py-1 rounded-full bg-gray-100">
              Преимущество 1/3
            </div>
          </div>

          <!-- Feature Title -->
          <h1 class="text-xl text-center font-bold">Максимально просто</h1>

          <!-- Emoji -->
          <div class="w-full flex justify-center mt-6">
            <img class="w-1/4" src="./icons/joystick.png" alt="Emoji" />
          </div>

          <!-- Text -->
          <p class="mt-4 text-sm text-gray-900 text-center px-6 lg:px-12">Мы стараемся делать все наши сервисы максимально простыми и интуитивно понятными. Именно поэтому мы гарантируем то, что вы чуть ли не моментально сможете разобраться в том, как именно работает каждый наш сервис!</p>

          <!-- Dots -->
          <div class="absolute inset-x-0 bottom-0 w-full py-2 flex justify-center items-center opacity-75">
            <div class="w-4 h-4 mx-2 rounded-full bg-black"></div>
            <div class="w-3 h-3 mx-2 rounded-full border-2 border-gray-900"></div>
            <div class="w-3 h-3 mx-2 rounded-full border-2 border-gray-900"></div>
          </div>
        </div>

        <!-- Background #2 -->
        <div in:slide={{ duration: 850 }} style="height: 35vh;" class="opacity-75 absolute bottom-0 right-0 w-2/3 shadow-xl bg-white rounded-t-lg">
          <!-- Badge -->
          <div class="w-full flex justify-center py-3">
            <div class="opacity-75 text-sm px-3 py-1 rounded-full bg-gray-100">
              Преимущество 2/3
            </div>
          </div>

          <!-- Feature Title -->
          <h1 class="text-xl text-center font-bold">Полностью бесплатно</h1>
        
          <!-- Emoji -->
          <div class="w-full flex justify-center mt-6">
            <img class="w-1/4" src="./icons/credit-card.png" alt="Emoji" />
          </div>

          <!-- Text -->
          <p class="mt-4 text-sm text-gray-900 text-center px-6 lg:px-12">Базовая версия любого нашего сервиса полностью бесплатна! Мы, будучи маленькой и безденежной командой, стараемся уменьшить количество ограничений для базовых версиях наших продуктов. Так же ни на одном сайте нету рекламы! Ну, как минимум, пока что.</p>

          <!-- Dots -->
          <div class="absolute inset-x-0 bottom-0 w-full py-2 flex justify-center items-center opacity-75">
            <div class="w-3 h-3 mx-2 rounded-full border-2 border-gray-900"></div>
            <div class="w-4 h-4 mx-2 rounded-full bg-black"></div>
            <div class="w-3 h-3 mx-2 rounded-full border-2 border-gray-900"></div>
          </div>
        </div>
      </section>
    </div>

    <!-- Services Panel -->
    <section style="z-index: 2;" id="services" class="w-full border-t-1 border-gray-300 h-min-screen relative px-6 lg:px-12 bg-white">
      <!-- Big Title -->
      <div class="w-full pt-8 pb-2 text-center">
        <h1 class="text-2xl text-black font-bold">Список сервисов</h1>
        <p class="text-md text-gray-900">Полный список всего того, что мы делаем.</p>
      </div>
      
      <!-- Fast Categories Skip -->
      <div class="w-full py-6 px-6 flex justify-center">
        { #each services as category }
          <div on:click={(e) => {
            if (category.status != 0) window.location.href = `#cat${ category.catId }`;
          }} class="{ category.status != 0 ? "cursor-pointer" : "opacity-75 cursor-not-allowed" } mx-2 px-4 py-2 rounded-full bg-gray-300 text-black text-base">
            { category.name }
          </div>
        { /each }
      </div>

      <!-- Services List -->
      { #each services as category }
        { #if category.status != 0 }
          <!-- Category Wrapper -->
          <div id="cat{ category.catId }" class="w-full pb-6 pt-2">
            <!-- Title -->
            <h1 class="text-2xl text-black">{ category.name }</h1>
            <p class="text-md text-gray-900">{ category.description }</p>

            <!-- Items -->
            <div class="w-full mt-4 relative flex">
              { #each category.items as service }
                <div class="w-1/2 relative">
                  <div style="padding-top: 50%;" class="w-full relative px-3 py-2">
                    <div class="absolute inset-0 w-full h-full flex-col justify-center items-center bg-{ service.color }">
                      <!-- Logotype -->
                      <div class="w-full flex items-center pt-4 px-4">
                        <img style="height: 2.6vw;" src="{ service.logotype }" alt="Service Logotype">
                        
                        { #if service.badges != null && service.badges.length > 0 }
                          <!-- Divider -->
                          <div style="height: 1.2rem; width: 1px;" class="bg-white rounded-md ml-2"></div>
                        
                          <!-- Badges -->
                          <div class="flex">
                            { #each service.badges as badge }
                              <div class="mx-1 text-sm px-1 py-1 rounded-full bg-{ badge.color } text-white">
                                { badge.text }
                              </div>
                            { /each }
                          </div>
                        { /if }
                      </div>
                        
                      <!-- Description -->
                      <p class="px-4 text-md my-3 text-white">{ service.description }</p>

                      <!-- Buttons -->
                      <div class="w-full flex absolute inset-x-0 bottom-0 py-2 px-4">
                        <!-- Goto -->
                        <button on:click={(e) => {
                          if (service.href != null) window.location.href = service.href;
                        }} class="mr-2 py-3 w-full px-4 { service.href != null ? "cursor-pointer" : "cursor-not-allowed opacity-75" } bg-black text-white flex items-center justify-center">
                          <!-- Text -->
                          <p class="text-base pr-2">Перейти</p>
            
                          <!-- Icon -->
                          <svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-right"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
                        </button>

                        <!-- Support -->
                        <button class="ml-2 py-3 w-full px-4 cursor-not-allowed opacity-75 bg-black text-white flex items-center justify-center">
                          <!-- Icon -->
                          <svg style="width: 1rem; height: 1rem;" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-heart"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
                          
                          <!-- Text -->
                          <p class="text-base pl-2">Поддержать</p>
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
              { /each }
            </div>
          </div>
        { /if }
      { /each }
    </section>

    <!-- Footer -->
    <footer class="w-full mt-12 flex justify-center bg-gray-100 pb-8 pt-12">
      <div class="opacity-75 flex flex-col items-center">
        <!-- Team Logotype -->
        <img style="height: 1.5vw;" src="./logotype/black.svg" alt="Unfull Team Logotype">
        <p class="text-sm text-gray-900 mt-2">unfull Team, 2020</p>
      </div>
    </footer>
	</main>
{ /if }