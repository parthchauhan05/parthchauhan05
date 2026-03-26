<script>
import { ref, computed } from "vue";

export default {
    data() {
        return {
            events: [
                {
                    type: 'work',
                    id: 1,
                    title: 'Software Engineer',
                    company: 'Orion Innovation (Bell Canada)',
                    endDate: 'Present',
                    startDate: 'October 2021',
                    work: [
                        'Led frontend modernization initiatives, upgrading applications from Vue 2 to Vue 3, refactoring 40+ reusable UI components, and aligning the platform with scalable Single Page Application (SPA) architecture standards.',
                        'Developed and maintained frontend modules using Vue and React, integrating 25+ REST API endpoints to support billing workflows and real-time account updates.',
                        'Designed and owned Java Spring Boot microservices supporting core billing logic for a SaaS platform serving 465,000+ consumers, handling monthly transactions with MongoDB backed invoice and usage data storage.',
                        'Implemented authentication and role-based authorization using Spring Security, configuring secure access controls for 10+ internal and external user groups across multi-tenant environments.',
                        'Containerized services using Docker and supported CI/CD pipelines via GitLab, contributing to 2–3 production releases per month and improving deployment reliability.',
                        'Trained and mentored 12 engineers in frontend development best practices, establishing reusable component standards and improving delivery consistency across new initiatives.',
                        'Participated in technical interviews and candidate evaluations as part of the hiring panel, supporting team expansion for a newly launched enterprise billing project.',
                        'Received a company recognition award in December 2025 for contributing to the formation and onboarding of the frontend team supporting a strategic billing initiative.',
                        // 'Developed and maintained unit tests for core functionalities, ensuring high code quality and reliability.',
                    ],
                    technology: [
                        { icon: 'tech/vue.svg', name: 'Vue.Js' },
                        { icon: 'tech/react.svg', name: 'React' },
                        { icon: 'tech/typescript.svg', name: 'TypeScript' },
                        { icon: 'tech/javascript.svg', name: 'JavaScript' },
                        { icon: 'tech/pinia.svg', name: 'Pinia' },
                        { icon: 'tech/html5.svg', name: 'HTML' },
                        { icon: 'tech/css3.svg', name: 'CSS' },
                        { icon: 'tech/scss.svg', name: 'SCSS' },
                        { icon: 'tech/Java.svg', name: 'Java' },
                        { icon: 'tech/Spring.svg', name: 'Spring Boot' },
                        { icon: 'tech/mongodb.svg', name: 'MongoDB' },
                    ]
                },
                // {
                //     type: 'work',
                //     id: 2,
                //     title: 'Web Developer',
                //     company: 'Digital Main Street | Invest Ottawa',
                //     endDate: 'July 2021',
                //     startDate: 'May 2021',
                //     work: [
                //         'Helped local businesses with website and/or online presentation.',
                //         'Modified existing Shopify store for better user experience.',
                //         'Worked on Wordpress website for local business.',
                //         'Developed online course platform using Thinkific.',
                //         'Enhanced SEO and Google Analytics for local businesses.',
                //     ],
                //     technology: [
                //         { icon: 'tech/shopify.svg', name: 'Shopify' },
                //         { icon: 'tech/wordpress.svg', name: 'Wordpress' },
                //         { icon: 'tech/thinkific.svg', name: 'Thinkific' },
                //         { icon: 'tech/google-analytics.svg', name: 'Google Analytics' },
                //     ]
                // },
                { 
                    type: 'study',
                    id: 2,
                    title: 'Diploma',
                    major: 'Interactive Media Design',
                    university: 'Algonquin College of Applied Arts and Technology (ACAT)',
                    universityShort: 'Algonquin College',
                    startDate: 'January 2019',
                    endDate: 'August 2020',
                    courseWork: ['UI/UX','Web Development','Project Management','HTML','CSS','JavaScript','Vue.js','Shopify'],
                },
                {
                    type: 'work',
                    id: 3,
                    title: 'Software Developer',
                    company: 'Airbnb',
                    endDate: 'December 2018',
                    startDate: 'December 2016',
                    work: [
                        'Developed backend services using Java and RESTful APIs, contributing to 8+ service modules supporting booking workflows and internal content management features used by regional operations teams.', 
                        'Built 25+ reusable UI components using React, JavaScript, HTML5, and CSS3, improving frontend maintainability and reducing duplicate UI logic across listing and booking pages.',
                        'Integrated frontend modules with 15+ backend REST API endpoints, collaborating with a 6-member backend team to ensure consistent request/response handling and reliable booking state transitions.',
                        'Optimized 20+ high-usage SQL queries and refined indexing strategies in MySQL, improving listing retrieval performance during peak evening traffic cycles.',
                        'Supported application deployments in AWS (EC2, S3) environments, contributing to 2+ production releases per month and assisting with environment validation across development and staging instances.',
                        'Worked within an Agile/Scrum team of 7 engineers, participating in bi-weekly sprint planning, reviewing 15+ pull requests per month, and contributing to feature estimation and technical design discussions.'
                    ],
                    technology: [
                        { icon: 'tech/react.svg', name: 'React' },
                        { icon: 'tech/typescript.svg', name: 'TypeScript' },
                        { icon: 'tech/javascript.svg', name: 'JavaScript' },
                        { icon: 'tech/html5.svg', name: 'HTML' },
                        { icon: 'tech/css3.svg', name: 'CSS' },
                        { icon: 'tech/scss.svg', name: 'SCSS' },
                        { icon: 'tech/Java.svg', name: 'Java' },
                        { icon: 'tech/Spring.svg', name: 'Spring Boot' },
                        { icon: 'tech/MySQL.svg', name: 'MySQL' },
                    ]
                },
                // {
                //     type: 'work',
                //     id: 5,
                //     title: 'Python Developer Intern',
                //     company: 'Punchit.io',
                //     endDate: 'July 2017',
                //     startDate: 'May 2017',
                //     work: [
                //         'Developed APIs for the mobile application using Django, Python and MongoDB.'
                //     ],
                //     technology: [
                //         { icon: 'tech/python.svg', name: 'Python' },
                //         { icon: 'tech/django.svg', name: 'Django' },
                //         { icon: 'tech/mongodb.svg', name: 'MongoDB' },
                //     ]
                // },
                // {
                //     type: 'work',
                //     id: 6,
                //     title: 'Python Developer Intern',
                //     company: 'ThingsXthings',
                //     endDate: 'December 2016',
                //     startDate: 'November 2016',
                //     work: [
                //         'Created desktop application using Python and Tkinter for prototype.',
                //         'Worked on algorithm enhancement for prototype.' 
                //     ],
                //     technology: [
                //         { icon: 'tech/python.svg', name: 'Python' },
                //         { icon: 'tech/tkinter.png', name: 'Tkinter' },
                //     ]
                // },
                { 
                    type: 'study',
                    id: 4,
                    title: 'Bachelors of Technology',
                    major: 'Information and Communication Technology',
                    university: 'Dhirubhai Ambani Institute of Information and Communication Technology (DA-IICT)',
                    universityShort: 'DA-IICT',
                    startDate: 'July 2014',
                    endDate: 'May 2018',
                    courseWork: ['Computer Programming','Database Management','Operating Systems','Web Technology','Software Testing','Software Engineering'],
                },
            ],
            activeItem: 1
        }
    },
    computed: {
        isMobile() {
            return window.innerWidth < 961
        },
        item() {
            return this.events[this.activeItem - 1]
        }
    },
    methods: {
        changeItem(val) {
            this.activeItem = val;
        }
    }
}
</script>

<template>
    <section class="education">
        <img class="wave wave-open" src="../assets/wave-open.svg"/>
        <div class="education-history">
            <h3>My Journey</h3>
            <i class="pi pi-ellipsis-h" style="font-size: 2rem;color: white;"></i>
            <div class="education-timeline" v-if="!isMobile">
                <div class="education-timeline-left">
                    <Timeline :value="events" class="customized-timeline">
                        <template #marker="slotProps">
                            <span class="education-timeline-marker" :class="slotProps.item.type" @click="changeItem(slotProps.item.id)">
                                <i class="pi pi-graduation-cap" v-if="slotProps.item.type === 'study'"></i>
                                <i class="pi pi-briefcase" v-else></i>
                            </span>
                        </template>
                        <template #content="slotProps">
                            <div class="education-timeline-item" :class="activeItem == slotProps.item.id ? 'active': ''">
                                <span class="pointer" @click="changeItem(slotProps.item.id)"> {{ slotProps.item.title }}, {{ slotProps.item.type === 'study' ? slotProps.item.university : slotProps.item.company }}</span>
                                <br />
                                <em class="education-timeline-period" :class="slotProps.item.type === 'study' ? 'study' : ''">({{ slotProps.item.startDate }} - {{ slotProps.item.endDate }})</em>
                            </div>
                        </template>
                    </Timeline>
                </div>
                <div class="education-timeline-right">
                    <Card class="education-timeline-card">
                        <template #title>
                            <h4>{{ item.title }}</h4>
                        </template>
                        <template #subtitle v-if="item.type === 'study'">
                            <em>{{ item.major }}</em>
                        </template>
                        <template #content v-if="item.type === 'study'">
                            <b>{{ item.university }}</b>
                            <br />
                            {{ item.startDate }} - {{ item.endDate }}
                            <br />
                            <small><b>Learnings:</b></small><br />
                            <Tag v-for="course in item.courseWork" :key="course">{{ course }}</Tag>
                        </template>
                        <template #content v-else>
                            <b>{{ item.company }}</b>
                            <br />
                            {{ item.endDate }} - {{ item.startDate }}
                            <br />
                            <small><b>Responsibilities:</b></small>
                            <ul>
                                <li v-for="work in item.work" :key="work">{{ work }}</li>
                            </ul>
                            <small><b>Technologies:</b></small>
                            <br />
                            <Chip 
                                v-for="tech in item.technology" 
                                :key="tech.name" 
                                :label="tech.name" 
                                :image="tech.icon"
                            />
                        </template>
                    </Card>
                </div>
            </div>
            <div class="education-accordian" v-else>
                <Accordion :value="[0]" multiple expandIcon="pi pi-plus" collapseIcon="pi pi-minus">
                    <AccordionPanel v-for="(item, id) in events" :key="id" :value="id">
                        <AccordionHeader>
                            <span class="education-accordian-header">
                                <span class="education-timeline-marker" :class="item.type">
                                    <i class="pi pi-graduation-cap" v-if="item.type === 'study'"></i>
                                    <i class="pi pi-briefcase" v-else></i>
                                </span>
                                <span class="education-accordian-header-title" :class="item.type === 'study' ? 'study' : ''">
                                    {{ item.title }}
                                    <br />
                                    <em>{{ item.type === 'study' ? item.universityShort : item.company }}</em>
                                </span>
                            </span>
                        </AccordionHeader>
                        <AccordionContent>
                            <Card class="education-timeline-card">
                                <template #title>
                                    <h4>{{ item.title }}</h4>
                                </template>
                                <template #subtitle v-if="item.type === 'study'">
                                    <em>{{ item.major }}</em>
                                </template>
                                <template #content v-if="item.type === 'study'">
                                    <b>{{ item.university }}</b>
                                    <br />
                                    {{ item.startDate }} - {{ item.endDate }}
                                    <br />
                                    <small><b>Learnings:</b></small><br />
                                    <Tag v-for="course in item.courseWork" :key="course">{{ course }}</Tag>
                                </template>
                                <template #content v-else>
                                    <b>{{ item.company }}</b>
                                    <br />
                                    {{ item.endDate }} - {{ item.startDate }}
                                    <br />
                                    <small><b>Responsibilities:</b></small>
                                    <ul>
                                        <li v-for="work in item.work" :key="work">{{ work }}</li>
                                    </ul>
                                    <small><b>Technologies:</b></small>
                                    <br />
                                    <Chip 
                                        v-for="tech in item.technology" 
                                        :key="tech.name" 
                                        :label="tech.name" 
                                        :image="tech.icon"
                                    />
                                </template>
                            </Card>  
                        </AccordionContent>
                    </AccordionPanel>
                </Accordion>
            </div>
        </div>
        <img class="wave wave-close" src="../assets/wave-close.svg"/>
    </section>
</template>

<style lang="scss">
    .education {
        width: 100%;
        margin: 0 auto;
        text-align: center;
        overflow: hidden;
        &-history {
            width: 100%;
            margin: 0 auto;
            background-color: var(--p-primary-400);
            padding: 0;
            color: white;
            h3 {
                font-size: 2.25rem;
                font-weight: 700;
                line-height: 2.5rem;
                margin: 0;
                color: white;
            }
        }
        &-timeline {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 30px;
            display: flex;
            flex-direction: row;
            gap: 2rem;
            justify-content: space-between;
            &-left {
                width: 40%;
                padding-top: 30px;
            }
            &-right {
                width: 60%;
            }
            &-period {
                color: #A3D9FF;
                &.study {
                    color: #03045E;
                }
            }
            h4 {
                font-size: 1.5rem;
                font-weight: 700;
                line-height: 1.75rem;
                margin: 0;
                color: var(--p-primary-color);
            }
            &-marker {
                display: flex;
                justify-content: center;
                align-items: center;
                cursor: pointer;
                width: 2rem;
                height: 2rem;
                border-radius: 50%;
                background-color: #03045E;
                box-shadow: 0px 10px 13px -7px #000000;
                &.work {
                    background-color: #A3D9FF;
                    i {
                        color: var(--p-primary-color)
                    }
                }
                i {
                    color: white;
                }
            }
            &-header {
                display: flex;
                // justify-content: space-between;
                align-items: center;
                gap: 20px;
                cursor: pointer;
                margin-bottom: 30px;
            }
            &-card.p-card {
                box-shadow: 0px 0px 15px -10px #000000;
                // margin-bottom: 30px;
                text-align: left;
                width: 90%;
                margin: 30px auto;
                margin-right: 0;
                @media screen and (max-width: 960px) {
                    width: 100%;
                }
                .p-card-title {
                    font-size: 1.5rem;
                    font-weight: 700;
                    line-height: 1.75rem;
                    color: var(--p-primary-color);
                    h4{
                        margin: 0;
                    }
                }
                .p-tag, .p-chip {
                    margin: 5px;
                }
            }
            .active {
                border-radius: 25px;
                font-weight: 700;
                background: var(--p-primary-800);
                box-shadow: 0px 10px 13px -7px #00000030;
                em {
                    color: #A3D9FF;
                }
            }
            &-item {
                padding: 5px 5px 5px 20px;
            }
        }
        .p-steppanel {
            background: inherit;
        }
        .p-stepitem {
            align-items: flex-start;
            padding: 0 30px;
        }
        .p-timeline-event-opposite {        
            display: none;
        }
        &-accordian {
            margin: 0 20px;
            &-header {
                display: flex;
                justify-content: flex-start;
                align-items: center;
                gap: 20px;
                cursor: pointer;
                &-title {
                    color: var(--p-primary-800);
                    text-align: left;
                }
            }
            .p-accordioncontent-content {
                background-color: var(--p-primary-400);
                padding: 1.5rem 0;
                .education-timeline-card.p-card {
                    margin: 0;
                    ul {
                        padding-inline-start: 25px;
                    }
                }
            }
        }
        img.wave {
            width: 102%;
            overflow: hidden;
            display: block;
            &.wave-close {
                margin-top: -5px;
            }
            &.wave-open {
                margin-bottom: -5px;
            }
        }
    }
    .pointer {
        cursor: pointer;
    }
</style>