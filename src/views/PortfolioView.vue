<script>
import sertif1 from '@/assets/sertif1.jpg';
import sertif2 from '@/assets/sertif2.png';
import sertif3 from '@/assets/sertif3.jpg';
import sertif4 from '@/assets/sertif4.jpg';
import sertif5 from '@/assets/sertif5.jpg';
import web1 from '@/assets/ukl.png';
import web2 from '@/assets/iot.png';
import web3 from '@/assets/cp.png';
import web4 from '@/assets/gloair.png';
import web5 from '@/assets/smartnote.png';
import web6 from '@/assets/inspire.png';




export default {
  data() {
    return {
      activeTab: 1, // 1 untuk Project, 2 untuk Sertifikat
      projects: [
        {
          id: 1,
          name: 'Project UKL',
          imageUrl: web1,
          status: 'My personal website, This website was created as a project for my UKL (Ujian Kenaikan Level) at school, showcasing my web development skills.',
          tech: 'PHP',
          // github: 'https://github.com/rakha-elctrnx/Portofolio-v2',
        },
        {
          id: 2,
          name: 'IoT Dashboard',
          imageUrl: web2,
          status: 'This website is a weather monitoring dashboard connected to an IoT system, collecting data from LDR and raindrop sensors.',
          tech: 'PHP, C++',
          // github: 'https://github.com/rakha-elctrnx/muslim-companion',
          // demo: 'https://sahabat-muslim.netlify.app/'
        },
        {
          id: 3,
          name: 'Company Profile',
          imageUrl: web3,
          status: 'This website is a commissioned project for a sandblasting company, designed to showcase their profile and services.',
          tech: 'PHP Laravel',
        },
        {
          id: 4,
          name: 'Mobile App for GloAir',
          imageUrl: web4,
          status: 'GloAir is an IoT-based system designed to monitor and improve air quality using a DHT11 sensor, an MQ7 sensor, and 3 relays to control fan1, fan2, and a pump.',
          tech: 'React Native, Nodejs, MQtt',
        },
        {
          id: 5,
          name: 'Smartnote',
          imageUrl: web5,
          status: 'SmartNote is a smart voice recorder and web app that helps teachers generate structured materials using AI.',
          tech: 'Python, Javascript',
        },
        {
          id: 6,
          name: 'Smart Seaweed Farming',
          imageUrl: web6,
          status: 'Developed an IoT-based water quality monitoring system for seaweed farming ',
          tech: 'PHP, Javascript',
        },
        {
          id:7,
          name: 'Tube Thickness Measurement',
          imageUrl: web6,
          status: 'Develops an IoT-based system to measure tube thickness for pharmaceutical packaging quality control. The device records real-time measurements automatically into a spreadsheet.',
          tech: 'PHP, Javascript',
        },
      ],
      certificates: [
        {
          id: 1,
          name: 'Ionic Iot Innovations',
          imageUrl:  sertif1,
          status: 'Certificate for contributing Ionic Iot Innovations event.',
          issuer: 'PENS Surabaya',
          date: '2 November 2024'
        },
        {
          id: 2,
          name: 'Sefest Web Dev',
          imageUrl: sertif2,
          status: 'Certificate for contributing Sefest Web Developement event.',
          issuer: 'Telkom University Surabaya',
          date: '13 July 2024'
        },
        {
          id: 3,
          name: 'Inspire IoT Competition',
          imageUrl: sertif3,
          status: 'Certificate of 2nd place on Insoire IoT Competition.',
          issuer: 'Universitas Gajah Mada',
          date: '30 November 2024'
        },
        {
          id: 4,
          name: 'Samsung Innovation Campus',
          imageUrl: sertif4,
          status: 'Certificate for contributing Samsung Innovations Campus Iot and Artificial Intellegence course.',
          issuer: 'Hacktiv8',
          date: 'December 2024'
        },
        {
          id: 5,
          name: 'Digicourse Cyber Security',
          imageUrl: sertif5,
          status: 'Certificate for contributing Digicourse Cyber Security course.',
          issuer: 'Yayasan Pendidikan Telkom',
          date: 'February 2024'
        },
      ]
    };
  }
}
</script>
<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <article data-page="portfolio">
      <header>
        <div class="text-2xl font-bold text-white mb-5 fadein-bot title-section flex items-center">
          <div class="h-[1px] w-10 bg-amber-200 md:w-20 aos-init aos-animate" data-aos="zoom-in-left"
            data-aos-duration="600"></div>
          &nbsp; Portfolio
        </div>
      </header>
      <section>
        <div>
          <ul class="flex flex-wrap text-sm font-medium text-center text-gray-500 dark:text-gray-400 mb-5">
            <li class="mr-2">
              <button class="inline-block px-4 py-3 rounded-lg hover:text-white"
                :class="{ 'text-amber-200 bg-amber-200 bg-opacity-10': activeTab === 1 }" @click="activeTab = 1">Projects</button>
            </li>
            <li class="mr-2">
              <button class="inline-block px-4 py-3 rounded-lg hover:text-white"
                :class="{ 'text-amber-200 bg-amber-200 bg-opacity-10': activeTab === 2 }" @click="activeTab = 2">Certificates</button>
            </li>
          </ul>
        </div>
        <div v-show="activeTab === 1">
          <div class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-3 md:gap-3 xl:grid-cols-3 xl:gap-3 2xl:gap-5 fade-zoom-in">
            <div v-for="item in projects" :key="item.id">
              <div
                class="item-card flex flex-col items-center gap-2 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] rounded-xl text-amber-50 md:gap-3 px-5 py-5 lg:px-5 ">
                <div class="flex h-12 w-12 items-center justify-center p-0 h-full w-full lg:p-0 zoom-in">
                  <img :alt="item.name" loading="lazy" decoding="async" data-nimg="1" class="drop-shadow-xl rounded rounded-xl"
                    :src="item.imageUrl"> <!-- Langsung gunakan item.imageUrl -->
                </div>
                <div class="w-full flex flex-col gap-2 items-center text-sm md:text-base lg:text-lg">
                  <div class="title-text font-medium text-secondary">{{ item.name }}</div>
                  <div class="w-full text-left text-[10px] text-[#c1c1c1] md:text-xs lg:text-sm">
                    {{ item.status }}</div>
                  <div class="w-full mt-4 text-normal text-sm text-left text-amber-200">
                    {{ item.tech }}
                  </div>
                  <div class="w-full flex justify-end">
                    <div class="flex cursor-pointer items-end gap-2 text-primary">
                      <a v-if="item.github !== 'null'"
                        :href="item.github" target="_blank" rel="noreferrer"
                        title="View github repository" class="transition-all hover:text-accent">
                        <svg stroke="currentColor"
                          fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"
                          height="16" width="16" xmlns="http://www.w3.org/2000/svg">
                          <path
                            d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22">
                          </path>
                        </svg>
                      </a>
                      <a v-if="item.demo !== 'null'" :href="item.demo" target="_blank" rel="noreferrer"
                        title="View finished project" class="transition-all hover:text-accent">
                        <svg stroke="currentColor"
                          fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"
                          height="18" width="18" xmlns="http://www.w3.org/2000/svg">
                          <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                          <polyline points="15 3 21 3 21 9"></polyline>
                          <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                      </a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-show="activeTab === 2">
          <div class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-3 md:gap-3 xl:grid-cols-3 xl:gap-3 2xl:gap-5 fade-zoom-in">
            <div v-for="item in certificates" :key="item.id">
              <div
                class="item-card flex flex-col items-center gap-2 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] rounded-xl text-amber-50 md:gap-3 px-5 py-5 lg:px-5 ">
                <div class="flex h-12 w-12 items-center justify-center p-0 h-full w-full lg:p-0 zoom-in">
                  <img :alt="item.name" loading="lazy" decoding="async" data-nimg="1" class="drop-shadow-xl rounded rounded-xl"
                    :src="item.imageUrl"> <!-- Langsung gunakan item.imageUrl -->
                </div>
                <div class="w-full flex flex-col gap-2 items-center text-sm md:text-base lg:text-lg">
                  <div class="title-text font-medium text-secondary">{{ item.name }}</div>
                  <div class="w-full text-left text-[10px] text-[#c1c1c1] md:text-xs lg:text-sm">
                    {{ item.status }}</div>
                  <div class="w-full mt-4 text-normal text-sm text-left text-amber-200">
                    Issuer: {{ item.issuer }}
                  </div>
                  <div class="w-full mt-2 text-normal text-sm text-left text-amber-200">
                    Date: {{ item.date }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>
<style>
.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
}
svg:hover{
  stroke: #ffdb70;
}
@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

/* Menggunakan animasi pada elemen yang diinginkan */
.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}
</style>