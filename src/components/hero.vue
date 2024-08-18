<script setup>

const downloadCv = async () => {
    const url = '../../parth-chauhan-resume.pdf';
    try {
        const response = await fetch(url);
        const blob = await response.blob();
        const downloadUrl = URL.createObjectURL(blob);

        const link = document.createElement('a');
        link.href = downloadUrl;
        link.download = 'parth-chauhan-resume.pdf'; // You can change the filename here
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);

        URL.revokeObjectURL(downloadUrl);
    } catch (error) {
        console.error('Error downloading the file', error);
    }
}

const hireMe = () => {
    window.open('mailto:parthchauhan05@gmail.com');
}
</script>
<template>
    <section class="hero">
        <div class="hero-info">
            <h3>Hello, I am Parth -</h3>
            <h2>I am an experienced Web Developer</h2>
            <p>I am currently working as a Software Engineer at Sryas Inc. I have completed my graduation in Information and Communication Technology. I have a diploma in Interactive Media Design, focused on UI/UX and Frontend Web Development.</p>
            <div class="hero-info-button-group">
                <Button rounded>
                    <i class="pi pi-envelope" @click="hireMe"></i>Hire me</Button>
                <Button outlined rounded @click="downloadCv">
                    <i class="pi pi-download"></i>Download CV</Button>
            </div>
            <div class="hero-info-social-links">
                <a href="https://github.com/parthchauhan05" target="_blank"><i class="pi pi-github" style="font-size: 1.5rem; color: #551A8B;"></i></a>
                <a href="https://www.linkedin.com/in/parthchauhan05/" target="_blank"><i class="pi pi-linkedin" style="font-size: 1.5rem; color: #551A8B;"></i></a>
                <a href="mailto:parthchauhan05@gmail.com" target="_blank"><i class="pi pi-google" style="font-size: 1.5rem; color: #551A8B;"></i></a> 
                <a href="https://wa.me/+16135012020" target="_blank"><i class="pi pi-whatsapp" style="font-size: 1.5rem; color: #551A8B;"></i></a>
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
            h3 {
                font-size: 1.5rem;
                font-weight: 500;
                line-height: 1.75rem;
                margin-bottom: 0;
                color: var(--p-primary-color);
            }
            h2 {
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
    @media screen and (max-width: 960px) {
    .hero {
        flex-direction: column-reverse;
        &-info {
            width: 100%;
        }
    }
}

</style>