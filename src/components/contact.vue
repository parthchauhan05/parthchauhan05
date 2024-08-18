<script setup>
</script>

<template>  
    <section class="contact">
        <img class="wave" src="../assets/wave-open.svg"/>
        <div class="contact-info">
            <h3>Contact</h3>
            <i class="pi pi-ellipsis-h" style="font-size: 2rem;color: white;"></i>
            <div class="contact-info-button-group">
                <Button as="a" href="tel:+16135012020" target="_blank" rounded severity="secondary">
                    <i class="pi pi-phone"></i>+1 613 501-2020</Button>
                <Button as="a" href="mailto:parthchauhan05@gmail.com" target="_blank" rounded severity="secondary">
                    <i class="pi pi-envelope"></i>parthchauhan05@gmail.com</Button>
                
            </div>
            <h4>Follow me on social media</h4>
            <div class="contact-info-social-links">
                <Button as="a" href="https://wa.me/+16135012020" target="_blank" rounded severity="secondary">
                    <i class="pi pi-whatsapp"></i>
                </Button>
                <Button rounded severity="secondary" as="a" href="https://github.com/parthchauhan05" target="_blank">
                    <i class="pi pi-github"></i>
                </Button>
                <Button rounded severity="secondary" as="a" href="https://www.linkedin.com/in/parthchauhan05/" target="_blank">
                    <i class="pi pi-linkedin"></i>
                </Button>
                <Button rounded severity="secondary" as="a" href="https://www.instagram.com/parth__chauhan/" target="_blank">
                    <i class="pi pi-instagram"></i>
                </Button>
            </div>
            <p>&copy; Parth Chauhan {{ new Date().getFullYear() }}. All rights reserved.</p>
        </div>
    </section>
</template>

<style lang="scss">
    .contact  {
        &-info {
            padding-bottom: 2rem;
            background-color: var(--p-primary-400);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 1rem;
            color: white;
            h3 {
                font-size: 2.25rem;
                font-weight: 700;
                line-height: 2.5rem;
                margin: 0;
                color: white;
            }
            h4 {
                font-size: 1.5rem;
                font-weight: 500;
                line-height: 1.75rem;
                margin-bottom: 0;
                color: white;
            }
            &-button-group {
                @media screen and (max-width: 960px) {
                    flex-direction: column;
                }
                display: flex;
                flex-direction: row;
                justify-content: center;
                align-items: center;
                gap: 1rem;
                margin-top: 1rem;
            }
            &-social-links {
                display: flex;
                flex-direction: row;
                justify-content: center;
                align-items: center;
                gap: 1rem;
                a.p-button {
                    text-decoration: none;
                }
            }
        }
        img.wave {
            width: 100%;
            display: block;
        }
    }
</style>