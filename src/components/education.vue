<script setup>
import { ref } from "vue";

const events = ref([
    {
        type: 'work',
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
        type: 'education',
        title: 'Diploma',
        major: 'Interactive Media Design',
        university: 'Algonquin College of Applied Arts and Technology (ACAT)',
        startDate: 'January 2019',
        endDate: 'August 2020',
        courseWork: ['UI/UX','Web Development','Project Management','HTML','CSS','JavaScript','Vue.js','Shopify'],
    },
    {
        type: 'work',
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
        type: 'education',
        title: 'Bachelors of Technology',
        major: 'Information and Communication Technology',
        university: 'Dhirubhai Ambani Institute of Information and Communication Technology (DA-IICT)',
        startDate: 'July 2014',
        endDate: 'May 2018',
        courseWork: ['Computer Programming','Database Management','Operating Systems','Web Technology','Software Testing','Software Engineering'],
    },
]);
</script>

<template>
    <section class="education">
        <img class="wave" src="../assets/wave-open.svg"/>
        <div class="education-history">
            <h3>My Journey</h3>
            <div class="education-timeline">
                <Timeline :value="events" class="customized-timeline">
                    <template #marker="slotProps">
                        <span class="education-timeline-marker" :class="slotProps.item.type">
                            <i class="pi pi-graduation-cap" v-if="slotProps.item.type === 'education'"></i>
                            <i class="pi pi-briefcase" v-else></i>
                        </span>
                    </template>
                    <template #opposite="slotProps">
                        <Card class="education-timeline-card" v-if="slotProps.item.type === 'education'">
                            <template #title>
                               <h4>{{ slotProps.item.title }}</h4>
                            </template>
                            <template #subtitle>
                                <em>{{ slotProps.item.major }}</em>
                            </template>
                            <template #content>
                                <b>{{ slotProps.item.university }}</b>
                                <br />
                                {{ slotProps.item.startDate }} - {{ slotProps.item.endDate }}
                                <br />
                                <small><b>Learnings:</b></small><br />
                                <Tag v-for="course in slotProps.item.courseWork" :key="course">{{ course }}</Tag>
                            </template>
                        </Card>
                    </template>
                    <template #content="slotProps">
                        <Card class="education-timeline-card" v-if="slotProps.item.type === 'work'">
                            <template #title>
                               <h4>{{ slotProps.item.title }}</h4>
                            </template>
                            <template #content>
                                <b>{{ slotProps.item.company }}</b>
                                <br />
                                {{ slotProps.item.endDate }} - {{ slotProps.item.startDate }}
                                <br />
                                <small><b>Responsibilities:</b></small>
                                <ul>
                                    <li v-for="work in slotProps.item.work" :key="work">{{ work }}</li>
                                </ul>
                                <small><b>Technologies:</b></small>
                                <br />
                                <Chip 
                                    v-for="tech in slotProps.item.technology" 
                                    :key="tech.name" 
                                    :label="tech.name" 
                                    :image="tech.icon"
                                />
                            </template>
                        </Card>
                    </template>
                </Timeline>
            </div>
        </div>
        <img class="wave" src="../assets/wave-close.svg"/>
    </section>
</template>

<style lang="scss">
    .education {
        width: 100%;
        margin: 0 auto;
        text-align: center;
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
                padding-bottom: 30px;
            }
        }
        &-timeline {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
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
            &-card.p-card {
                box-shadow: 0px 10px 13px -7px #000000;
                margin-bottom: 30px;
            }
            .p-tag {
                margin: 5px;
            }
            .p-chip {
                margin: 5px;
            }
        }
        img.wave {
            width: 100%;
            display: block;
        }
    }
</style>