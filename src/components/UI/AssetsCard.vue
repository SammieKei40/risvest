<template>
    <div class="asset-card">
        <div class="curved-background" :style="{ backgroundColor: backgroundClass }">
            <div class="icon-container">
                <img :src="image" :alt="title" class="icon-image" />
            </div>
        </div>
        <div class="asset">


            <h3 class="asset-title">{{ title }}</h3>
            <p class="asset-description">{{ description }}</p>
            <p class="asset-info">
                <span class="highlight">Historical returns:</span> 14% per annum
            </p>
            <p class="asset-info">
                <span class="highlight">Risk Level:</span> Medium
            </p>
            <div class="link-wrapper">
                <a href="#" class="asset-link" aria-label="Learn more about {{ title }}">
                    {{ linkText }}
                    <Arrow />
                </a>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import Arrow from '../icons/arrow.vue';
import { defineProps } from 'vue';

interface Props {
    title: string;
    description: string;
    image: string;
    backgroundClass: string;
    linkText: string;
}

const props = defineProps<Props>();
</script>

<style scoped>
/* Asset Card */
.asset-card {
    background-color: #ffffff;
    border-radius: 0.5rem;
    border: 2px solid rgba(145, 159, 181, 0.20);
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    transition: transform 0.2s ease-in-out;
    height: 100%;
    justify-content: space-between;
    max-width: 25rem;
    margin: auto;
    /* height: 512px; */
}

.asset {
padding: 1rem;
margin-top: 1rem
}
a {
    text-decoration: none;
}

ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
}

ol {
    list-style-type: none;
    padding: 0;
    margin: 0;
}

.asset-card:hover {
    transform: translateY(-5px);
}

/* Curved Background */
.curved-background {
    width: 100%;
    height: 6rem;
    background-color: backgroundClass;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    margin-bottom: 1.5rem;
    border-radius: 0.5rem 0.5rem 0 0;
    z-index: 1;
    margin-bottom: 3rem;
}



/* Icon Container */
.icon-container {
    width: 5rem;
    height: 5rem;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #ffffff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    position: absolute;
    bottom: -2.5rem;
    z-index: 2;
}

.icon-image {
    width: 85px;
    height: 85px;
    flex-shrink: 0;
}

/* Text Content */
.asset-title {
    font-size: 24px;
    color: #4A5050;
    margin-bottom: 1rem;
    font-style: normal;
    font-weight: 600;
    line-height: 30px;
    letter-spacing: -1.2px;
}

.asset-description {
    color: #4a4a4a;
    text-align: center;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: -0.8px;
}

.asset-info {
    font-size: 1rem;
    color: #6b6b6b;
    margin-bottom: 0.1rem;
}

/* Highlighted text */
.highlight {
    font-weight: 400;
    color: #919FB5;
}

/* Link Wrapper to keep link aligned at bottom */
.link-wrapper {
    margin-top: auto;
    padding-top: 4rem;
}

/* Call-to-Action Link */
.asset-link {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 90%;
    letter-spacing: -0.8px;
    color: #07969E;
}

.asset-link:hover {
    text-decoration: underline;
}

/* Accessibility */
.asset-link:focus,
.icon-image:focus {
    outline: 2px solid #07969E;
    outline-offset: 2px;
}
</style>