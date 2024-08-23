<script>
import { ref, computed } from "vue";

export default {
    data() {
        return {
            events: [
                {
                    type: 'work',
                    id: 1,
                    title: 'Associate Software Engineer',
                    company: 'Sryas Inc.',
                    endDate: 'Present',
                    startDate: 'October 2021',
                    work: [
                        'Leading Front-end development team since January 2024.',
                        'Creating reusable code and components for future use with Vue, Pinia, JavaScript, TypeScript, and SCSS.',
                        'Collaborating with cross-functional teams to implement new features.',
                        'Participating in agile ceremonies, code reviews and pair programming.',
                        'Working with the design team to ensure the design of the UI/UX.',
                        'Trained around 10 developers in 1 month and improved their skills.',
                        'Successfully upgraded the project from Vue 2 to Vue 3 with major library updates.',
                        'Utilizing GitLab for version control and created/merged multiple pull requests daily, contributing to a 50% increase in task success rate.',
                        'Developed and maintained unit tests for core functionalities, ensuring high code quality and reliability.',
                    ],
                    technology: [
                        { icon: 'tech/vue.svg', name: 'Vue.Js' },
                        { icon: 'tech/scss.svg', name: 'SCSS' },
                        { icon: 'tech/javascript.svg', name: 'JavaScript' },
                        { icon: 'tech/typescript.svg', name: 'TypeScript' },
                        { icon: 'tech/pinia.svg', name: 'Pinia' },
                        { icon: 'tech/css3.svg', name: 'CSS' },
                        { icon: 'tech/html5.svg', name: 'HTML' },
                        { icon: 'tech/element-plus.svg', name: 'Element Plus' },
                    ]
                },
                {
                    type: 'work',
                    id: 2,
                    title: 'Web Developer',
                    company: 'Digital Main Street | Invest Ottawa',
                    endDate: 'July 2021',
                    startDate: 'May 2021',
                    work: [
                        'Helped local businesses with website and/or online presentation.',
                        'Modified existing Shopify store for better user experience.',
                        'Worked on Wordpress website for local business.',
                        'Developed online course platform using Thinkific.',
                        'Enhanced SEO and Google Analytics for local businesses.',
                    ],
                    technology: [
                        { icon: 'tech/shopify.svg', name: 'Shopify' },
                        { icon: 'tech/wordpress.svg', name: 'Wordpress' },
                        { icon: 'tech/thinkific.svg', name: 'Thinkific' },
                        { icon: 'tech/google-analytics.svg', name: 'Google Analytics' },
                    ]
                },
                { 
                    type: 'study',
                    id: 3,
                    title: 'Diploma',
                    major: 'Interactive Media Design',
                    university: 'Algonquin College of Applied Arts and Technology (ACAT)',
                    startDate: 'January 2019',
                    endDate: 'August 2020',
                    courseWork: ['UI/UX','Web Development','Project Management','HTML','CSS','JavaScript','Vue.js','Shopify'],
                },
                {
                    type: 'work',
                    id: 4,
                    title: 'Web Developer',
                    company: 'WiseL',
                    endDate: 'December 2018',
                    startDate: 'December 2016',
                    work: [
                        'Developed APIs for the web application and mobile application using Flask, Python, Firebase and MongoDB.', 
                        'Worked in an incubator startup with new challenges everyday.',
                        'Mentored 2 interns for web development.'
                    ],
                    technology: [
                        { icon: 'tech/python.svg', name: 'Python' },
                        { icon: 'tech/flask.svg', name: 'Flask' },
                        { icon: 'tech/mongodb.svg', name: 'MongoDB' },
                        { icon: 'tech/firebase.svg', name: 'Firebase' },
                    ]
                },
                {
                    type: 'work',
                    id: 5,
                    title: 'Python Developer Intern',
                    company: 'Punchit.io',
                    endDate: 'July 2017',
                    startDate: 'May 2017',
                    work: [
                        'Developed APIs for the mobile application using Django, Python and MongoDB.'
                    ],
                    technology: [
                        { icon: 'tech/python.svg', name: 'Python' },
                        { icon: 'tech/django.svg', name: 'Django' },
                        { icon: 'tech/mongodb.svg', name: 'MongoDB' },
                    ]
                },
                {
                    type: 'work',
                    id: 6,
                    title: 'Python Developer Intern',
                    company: 'ThingsXthings',
                    endDate: 'December 2016',
                    startDate: 'November 2016',
                    work: [
                        'Created desktop application using Python and Tkinter for prototype.',
                        'Worked on algorithm enhancement for prototype.' 
                    ],
                    technology: [
                        { icon: 'tech/python.svg', name: 'Python' },
                        { icon: 'tech/tkinter.png', name: 'Tkinter' },
                    ]
                },
                { 
                    type: 'study',
                    id: 7,
                    title: 'Bachelors of Technology',
                    major: 'Information and Communication Technology',
                    university: 'Dhirubhai Ambani Institute of Information and Communication Technology (DA-IICT)',
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
            <!-- <Stepper :value="stepper" class="education-timeline">
                <StepItem v-for="(item, index) in events" :key="index" :value="index+1" >
                    <Step v-slot="{ activateCallback }" asChild>
                        <div class="education-timeline-header" @click="activateCallback">
                                <span class="education-timeline-marker" :class="item.type">
                                    <i class="pi pi-graduation-cap" v-if="item.type === 'education'"></i>
                                    <i class="pi pi-briefcase" v-else></i>
                                </span>
                                {{ item.title }}, {{ item.type === 'education' ? item.university : item.company }}
                        </div>
                        <Divider layout="vertical" />
                    </Step>
                    <StepPanel v-slot="{ activateCallback }">
                        <Card class="education-timeline-card">
                            <template #title>
                               <h4>{{ item.title }}</h4>
                            </template>
                            <template #subtitle v-if="item.type === 'education'">
                                <em>{{ item.major }}</em>
                            </template>
                            <template #content v-if="item.type === 'education'">
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
                    </StepPanel>
                </StepItem>
            </Stepper> -->

            <div class="education-timeline">
                <div class="education-timeline-left">
                    <!-- <div class="education-timeline-header" @click="activateCallback" v-for="(item, index) in events" :key="index">
                            <span class="education-timeline-marker" :class="item.type">
                                <i class="pi pi-graduation-cap" v-if="item.type === 'study'"></i>
                                <i class="pi pi-briefcase" v-else></i>
                            </span>
                            
                            {{ item.title }}
                    </div> -->
                    <Timeline :value="events" class="customized-timeline">
                        <template #marker="slotProps">
                            <span class="education-timeline-marker" :class="slotProps.item.type" @click="changeItem(slotProps.item.id)">
                                <i class="pi pi-graduation-cap" v-if="slotProps.item.type === 'study'"></i>
                                <i class="pi pi-briefcase" v-else></i>
                            </span>
                        </template>
                        <!-- <template #opposite="slotProps">
                            <span>{{ slotProps.item.startDate }} - {{ slotProps.item.endDate }}</span>
                        </template> -->
                        <template #content="slotProps">
                            <span class="pointer" @click="changeItem(slotProps.item.id)"> {{ slotProps.item.title }}, {{ slotProps.item.type === 'study' ? slotProps.item.university : slotProps.item.company }}</span>
                            <br />
                            <em class="education-timeline-period" :class="slotProps.item.type === 'study' ? 'study' : ''">({{ slotProps.item.startDate }} - {{ slotProps.item.endDate }})</em>
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
            padding-top: 30px;
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