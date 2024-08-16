<script setup>

</script>
<template>
    <section class="hero">
        <div class="hero-info">
            <h4>Hello, I am Parth --</h4>
            <h3>I am an experienced Web Developer</h3>
            <p>I am currently working as a Software Engineer at Sryas Inc. I have completed my graduation in Information and Communication Technology. I have a diploma in Interactive Media Design, focused on UI/UX and Frontend Web Development.</p>
            <div class="hero-info-button-group">
                <Button rounded>
                    <i class="pi pi-envelope"></i>Hire me</Button>
                <Button outlined rounded>
                    <i class="pi pi-download"></i>Download CV</Button>
            </div>
            <div class="hero-info-social-links">
                <i class="pi pi-github"></i>
                <i class="pi pi-linkedin"></i>
                <i class="pi pi-google"></i>
                <i class="pi pi-whatsapp"></i>
            </div>
        </div>
        <div class="hero-image">
            <img src="../assets/parth.svg" alt="Parth. " width="250"/>
        </div>
    </section>
</template>
<style lang="scss">
    .hero {
        width: 100%;
        max-width: 1200px;
        margin: 0 auto; 
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        padding: 60px 30px;
        // border-bottom: 1px solid #e5e5e5;

        &-image {
            img {
                border-radius: 50%; 
                // border: 2px dashed #00377870;
                padding: 15px;
                box-shadow: inset 0px 0px 25px 5px #00377870;
            }
        }

        &-info {
            width: 60%;
            max-width: 720px;
            h4 {
                font-size: 1.5rem;
                font-weight: 500;
                line-height: 1.75rem;
                margin-bottom: 0;
                color: var(--p-primary-color);
            }
            h3 {
                font-size: 2.25rem;
                font-weight: 700;
                line-height: 2.5rem;
                margin-bottom: 1rem ; 
                margin-top: 0.25rem;
                color: var(--p-highlight-color);
            }
            p {
                max-width: 90%;
            }
            &-button-group {
                display: flex;
                flex-direction: row;
                justify-content: flex-start;
                align-items: center;
                gap: 1rem;
                margin-top: 1rem;
            }
            &-social-links {
                display: flex;
                flex-direction: row;
                justify-content: flex-start;
                align-items: center;
                gap: 1rem;
                margin-top: 1rem;
            }
        }
    }
</style>