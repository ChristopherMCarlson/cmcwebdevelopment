<template>
    <v-container>
        <v-row class="pt-5 justify-center">
            <v-col cols="5" v-if="!isMobile" id="table-of-contents" class="sticky">
                <v-row>
                    <v-col cols="8">
                        <div class="font-weight-black text-h3">Chris Carlson</div>
                        <div class="text-h5">Full Stack Developer</div>
                        <div class="text-h5 font-weight-thin">I build sleek, stylish, and functional websites and
                            software solutions
                        </div>
                        <div id="about-menu-item" class="d-flex align-center mt-5 hover-parent"
                            @click="scrollTo('about')">
                            <span :class="{ 'line': true, 'active-line': activeSection === 'about' }"></span>
                            <span>About</span>
                        </div>
                        <div id="projects-menu-item" class="d-flex align-center mt-5 hover-parent"
                            @click="scrollTo('projects')">
                            <span :class="{ 'line': true, 'active-line': activeSection === 'projects' }"></span>
                            <span>Projects</span>
                        </div>
                        <div id="skills-menu-item" class="d-flex align-center mt-5 hover-parent"
                            @click="scrollTo('skills')">
                            <span :class="{ 'line': true, 'active-line': activeSection === 'skills' }"></span>
                            <span>Skills</span>
                        </div>
                        <div id="experience-menu-item" class="d-flex align-center mt-5 hover-parent"
                            @click="scrollTo('experience')">
                            <span :class="{ 'line': true, 'active-line': activeSection === 'experience' }"></span>
                            <span>Experience</span>
                        </div>
                    </v-col>
                </v-row>
            </v-col>
            <v-col cols="12" md="5" id="contents">
                <v-row>
                    <v-col id="about-item" cols="12" class="section" ref="about">
                        <div class="font-weight-thin text-h3 mb-3" v-if="isMobile">About Me</div>
                        <p class="font-weight-light">
                            I am a passionate and detail-oriented Software Engineer with over six years of experience
                            developing
                            robust, scalable, and user-centric applications. My expertise spans a wide array of modern
                            technologies,
                            including React, Vue, Angular, JavaScript, and TypeScript for frontend development, and
                            Node.js,
                            Redis,
                            and AWS for backend and infrastructure.
                            <br>
                            <br>
                            I thrive on solving complex problems and building intuitive, efficient solutions that
                            enhance user
                            experience. My experience with Salesforce and Apex has further honed my ability to integrate
                            diverse
                            platforms seamlessly and streamline business processes.
                            <br>
                            <br>
                            From designing efficient architectures to deploying cloud-native solutions, I have a proven
                            track
                            record
                            of delivering high-quality products within agile environments. I take pride in staying
                            up-to-date
                            with the
                            latest tech trends and enjoy collaborating with cross-functional teams to turn innovative
                            ideas into
                            reality.
                            <br>
                            <br>
                            Beyond coding, I am committed to fostering clean code practices, mentoring peers, and
                            contributing
                            to team
                            success through collaboration and knowledge sharing. Whether it's creating a dynamic
                            single-page
                            application or optimizing server-side performance, I am driven by a passion for excellence
                            and
                            continuous
                            improvement.
                        </p>
                    </v-col>
                    <v-col id="projects-item" cols="12" class="section" ref="projects">
                        <div class="font-weight-thin text-h3 mb-3" v-if="isMobile">Projects</div>
                        <v-row v-for="project in projects" :key="project.image">
                            <v-col cols="12" md="3">
                                <a :href="project.link" target="_blank">
                                    <v-img :src="project.image"></v-img>
                                </a>
                            </v-col>
                            <v-col cols="12" md="3">
                                <div class="font-weight-thin text-h3">{{ project.name }}</div>
                                <div class="font-weight-light">{{ project.description }}</div>
                            </v-col>
                        </v-row>
                    </v-col>
                    <v-col id="skills-item" cols="12" class="section" ref="skills">
                        <div class="font-weight-thin text-h3 mb-3" v-if="isMobile">Skills</div>
                        <v-row>
                            <v-col cols="2" v-for="skill in frontendSkills" :key="skill.logo">
                                <a :href="skill.link" target="_blank">
                                    <v-img :src="skill.logo"></v-img>
                                </a>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col cols="2" v-for="skill in backendSkills" :key="skill.logo">
                                <a :href="skill.link" target="_blank">
                                    <v-img :src="skill.logo"></v-img>
                                </a>
                            </v-col>
                        </v-row>
                    </v-col>
                    <v-col id="experience-item" cols="12" class="section" ref="experience">
                        <div class="font-weight-thin text-h3 mb-3" v-if="isMobile">Experience</div>
                        <v-row v-for="job in jobs" :key="job.logo">
                            <v-col cols="12" md="3">
                                <v-img :src="job.logo"></v-img>
                            </v-col>
                            <v-col cols="12" md="9">
                                <div class="font-weight-thin text-h3">{{ job.title }}</div>
                                <div>{{ job.company }}</div>
                                <div>{{ job.date }}</div>
                                <ul>
                                    <li v-for="description in job.description" :key="description">{{ description }}</li>
                                </ul>
                            </v-col>
                        </v-row>
                    </v-col>
                </v-row>

            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { nextTick } from 'vue';

export default {
    data() {
        return {
            projects: [
                {
                    name: 'Tender',
                    image: require('@/assets/projects/tender.png'),
                    description: 'An app that allows users to save recipes they like, add friends, and see when friends have saved the same recipe.',
                    link: 'https://tender.cmcwebdevelopment.com/'
                }
            ],
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
                    date: '11/2018 - 06/2021',
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
            ],
            activeSection: 'about',
        };
    },
    methods: {
        scrollTo(section) {
            const element = this.$refs[section];
            if (element && element.$el) {
                element.$el.scrollIntoView({ behavior: 'smooth' });
            } else if (element) {
                element.scrollIntoView({ behavior: 'smooth' });
            }
        },
        handleIntersection(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    console.log(`Intersecting: ${entry.target.id}`);
                    this.activeSection = entry.target.id.replace('-item', '');
                }
            });
        }
    },
    mounted() {
        nextTick(() => {
            const options = {
                root: null,
                rootMargin: '0px 0px -80% 0px',
                threshold: 0.1
            };

            this.observer = new IntersectionObserver(this.handleIntersection, options);

            this.$refs.about && this.observer.observe(this.$refs.about.$el || this.$refs.about);
            this.$refs.projects && this.observer.observe(this.$refs.projects.$el || this.$refs.projects);
            this.$refs.skills && this.observer.observe(this.$refs.skills.$el || this.$refs.skills);
            this.$refs.experience && this.observer.observe(this.$refs.experience.$el || this.$refs.experience);
        });
    },
    beforeUnmount() {
        this.observer.disconnect();
    },
    computed: {
        isMobile() {
            return this.$vuetify.display.mobile;
        },
    },

}
</script>

<style scoped>
.section {
    margin-bottom: 100px;
}

.sticky {
    position: -webkit-sticky;
    position: sticky;
    top: 0;
    height: 90vh;
}

.line {
    display: block;
    width: 50px;
    height: 1px;
    background-color: white;
    margin-right: 10px;
    transition: width 0.3s ease;
}

.hover-parent:hover .line {
    width: 75px;
}

.active-line {
    display: block;
    width: 75px;
    height: 1px;
    background-color: white;
    margin-right: 10px;
    transition: width 0.3s ease;
}
</style>