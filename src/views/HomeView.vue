<template>
  <v-container>
    <v-row class="justify-center">
      <v-col cols="12" md="9">
        <v-row>
          <v-col cols="12" class="text-center">
            <h1 class="display-1">About Me</h1>
          </v-col>
        </v-row>
        <v-row class="mb-1" :class="isMobile ? 'justify-center' : ''">
          <v-col cols="6" v-if="isMobile" class="text-center">
            <v-img
              :src="require('@/assets/me.jpg')"
              alt="Chris Carlson"
            ></v-img>
          </v-col>
          <v-col :cols="[isMobile ? '12' : '9']">
            <h1>Hello, I'm Chris Carlson</h1>
            <p>
              I am a passionate and detail-oriented Software Engineer with over six years of experience developing robust, scalable, and user-centric applications. My expertise spans a wide array of modern technologies, including React, Vue, Angular, JavaScript, and TypeScript for frontend development, and Node.js, Redis, and AWS for backend and infrastructure.
              <br>
              <br>
              I thrive on solving complex problems and building intuitive, efficient solutions that enhance user experience. My experience with Salesforce and Apex has further honed my ability to integrate diverse platforms seamlessly and streamline business processes.
              <br>
              <br>
              From designing efficient architectures to deploying cloud-native solutions, I have a proven track record of delivering high-quality products within agile environments. I take pride in staying up-to-date with the latest tech trends and enjoy collaborating with cross-functional teams to turn innovative ideas into reality.
              <br>
              <br>
              Beyond coding, I am committed to fostering clean code practices, mentoring peers, and contributing to team success through collaboration and knowledge sharing. Whether it's creating a dynamic single-page application or optimizing server-side performance, I am driven by a passion for excellence and continuous improvement.
            </p>
          </v-col>
          <v-col cols="3" v-if="!isMobile">
            <v-img
              :src="require('@/assets/me.jpg')"
              width="300px"
              height="300px"
              alt="Chris Carlson"
            ></v-img>
          </v-col>
        </v-row>
        <v-divider></v-divider>
        <v-row class="mb-1">
          <v-col cols="12" class="text-center">
            <h1 class="display-1">Skills</h1>
          </v-col>
          <v-col cols="12">
            <v-row>
              <v-col cols="12">
                <v-row>
                  <v-col cols="12" :class="isMobile ? 'text-center' : ''">
                    <h2>Frontend</h2>
                  </v-col>
                  <v-col cols="12">
                    <v-row :class="isMobile ? 'justify-space-around' : ''">
                      <v-col
                        v-for="(skill, i) in frontendSkills"
                        :key="i"
                        cols="2"
                        class="text-center"
                      >
                      <a :href="skill.link" target="_blank">
                        <v-img
                          :src="skill.logo"
                          alt="Skill logo"
                          width="200"
                            >
                            </v-img>
                              </a>
                          <!-- <a :href="skill.link" target="_blank">{{ skill.name }}</a> -->
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
              </v-col>
              <v-col cols="12">
                <v-row>
                  <v-col cols="12" :class="isMobile ? 'text-center' : ''">
                    <h2>Backend</h2>
                  </v-col>
                  <v-col cols="12">
                    <v-row :class="isMobile ? 'justify-space-around' : ''">
                      <v-col
                        v-for="(skill, i) in backendSkills"
                        :key="i"
                        cols="2"
                        class="text-center"
                      >
                          <v-img
                            :src="skill.logo"
                            alt="Skill logo"
                            width="200"
                          ></v-img>
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-divider></v-divider>
        <v-row>
          <v-col cols="12" class="text-center">
            <h1 class="display-1">Experience</h1>
          </v-col>
          <v-col cols="12">
            <v-row>
              <v-col
                v-for="(job, i) in jobs"
                :key="i"
                cols="12"
              >
              <v-row class="mb-1">
                <v-col cols="3">
                  <v-img
                    :src="job.logo"
                    alt="Job logo"
                    width="200"
                  ></v-img>
                </v-col>
                <v-col :cols="[isMobile ? '12' : '9']">
                  <h2>{{ job.title }}</h2>
                  <h3>{{ job.company }} - {{ job.date }}</h3>
                  <ul>
                    <li v-for="(description, i) in job.description" :key="i">{{ description }}</li>
                  </ul>
                </v-col>
              </v-row>
              <v-divider></v-divider>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HomeView',
  data() {
    return {
      frontendSkills: [
        {
          name: 'JavaScript',
          logo: require('@/assets/skillsLogos/frontend/javascript.png'),
          link: 'https://developer.mozilla.org/en-US/docs/Web/JavaScript',
        },
        {
          name: 'TypeScript',
          logo: require('@/assets/skillsLogos/frontend/typescript.png'),
          link: 'https://www.typescriptlang.org/',
        },
        {
          name: 'Vue',
          logo: require('@/assets/skillsLogos/frontend/vue.png'),
          link: 'https://vuejs.org/',
        },
        {
          name: 'React',
          logo: require('@/assets/skillsLogos/frontend/react.png'),
          link: 'https://reactjs.org/',
        },
        {
          name: 'Angular',
          logo: require('@/assets/skillsLogos/frontend/angular.png'),
          link: 'https://angular.io/',
        },
      ],
      backendSkills: [
        {
          name: 'Node.js',
          logo: require('@/assets/skillsLogos/backend/nodeJS.png'),
          link: 'https://nodejs.org/',
        },
        {
          name: 'Express',
          logo: require('@/assets/skillsLogos/backend/expressJS.png'),
          link: 'https://expressjs.com/',
        },
        {
          name: 'AWS',
          logo: require('@/assets/skillsLogos/backend/AWS.png'),
          link: 'https://aws.amazon.com/',
        },
        {
          name: 'Docker',
          logo: require('@/assets/skillsLogos/backend/docker.png'),
          link: 'https://www.docker.com/',
        },
        {
          name: 'Redis',
          logo: require('@/assets/skillsLogos/backend/redis.png'),
          link: 'https://redis.io/',
        }
      ],
      jobs: [
        {
          title: 'Software Engineer',
          company: 'Buyers Edge Platform',
          date: '08/2021 - 11/2024',
          description: [
            'Lead Backend engineer on a brand new product to enhance manufacturer relations',
            'Conducted QA for internal design and development',
            'Oversaw hotfix needs; built and deployed solutions quickly',
            'Lead Frontend Engineer on a massive product rewrite',
            'Wrote extensive code in Angular, NodeJS, SQL, Redis, and TypeScript',
            'Took over as project manager on large product rewrite',
          ],
          logo: require('@/assets/jobs/buyersEdgePlatform.png'),
        },
        {
          title: 'Software Engineer',
          company: 'Verified First',
          date: '11/2019 - 06/2021',
          description: [
            'Part of a three person development team in charge of internal software development.',
            'Met with internal employees to discover, plan, and develop solutions to optimize workflow',
            'Conducted QA for internal design and development',
            'Administered hotfixes to ensure smooth daily operations',
            'Served as a thought partner for the Director of Information Systems',
            'Programmed back-end and front-end code within SalesForce',
            'Planned and executed application rewrite from NodeJS/Angular to Vue.Js/Laravel',
          ],
          logo: require('@/assets/jobs/verifiedFirst.png'),
        },
        {
          title: 'Full Stack Developer Student',
          company: 'CodeWorks',
          date: '07/2018 - 10/2018',
          description: [
            'Completed over 500 hours of software development in an immersive learning environment.',
            'Participated in 24-hour hack-a-thons events testing and challenging personal goals.',
            'Designed a music playlist app (Vue Music) where users search and add favorite artists to personalized lists. Integrated with iTunes Api, and built with VueJS.',
            'Utilized VueJS, node, and Vuetify to develop a user dashboard app displaying current weather, time, and rotating quotes and images. ',
            'Collaborated on group capstone project (Lendr), created an app to track status of loaned items to other users and allowed users to confirm receipt of lent items with attached due dates. Developed with VueJS, Vuetify, and Socket.io.',
            'Collaborated on a group project (Post-It) during 24-hour hack-a-thon to create a messaging board that allowed users to create accounts, start discussion threads, comment on threads, and provide feedback on comments and posts via a voting system.',
            'Spent time learning Vuetify for VueJS in order to better style web apps.'
          ],
          logo: require('@/assets/jobs/codeworks.png'),
        },
        {
          title: 'Biller',
          company: 'Saia LTL Freight',
          date: '04/2014 - 04/2018',
          description: [
            'Maintained private billing information and verified customer accounts through security protocols and procedures.',
            'Identified errors in customer processing forms, and ensured accurate adjustments were applied to prevent freight delays.',
          ],
          logo: require('@/assets/jobs/saiaLTLFreight.png'),
        },
        {
          title: 'Fire Support Specialist',
          company: 'US Army',
          date: '07/2011 - 03/2014',
          description: [
            'Received promotion and awarded Army Achievement Medal for excellent driving of a specialized vehicle.',
            'Honored Commendations: Army Service Ribbon, Global War on Terror Service Medal, National Defense Service.',
            'Managed transportation and communication efforts for armored vehicles and ensuring safe drivable conditions.',
            'Utilized understanding of advanced math to guarantee accuracy of quick calculations and prevent errors.',
          ],
          logo: require('@/assets/jobs/USArmy.png'),
        }
      ]
    };
  },
  components: {
  },
  computed: {
    isMobile() {
      return this.$vuetify.display.mobile;
    },
  },
});
</script>

