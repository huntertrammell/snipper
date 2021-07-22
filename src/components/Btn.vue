<template>
    <a :href="url" class="btn">{{ text }}<span>{{ caption }}</span></a>
</template>
<script>
export default {
    props: {
        url: String,
        text: String,
        caption: String
    }
}
</script>
<style lang="scss">
$black: black;
$gray: lightgray;
$white: white;
.btn {
    display: inline-block;
    color: $white;
    text-decoration: none;
    padding: 1rem 2rem;
    font-size: 2rem;
    span {
        color: $gray;
    }
    background-color: $black;
    box-shadow: 0px 3px 10px -4px rgba(0,0,0,0.4);
    transform: translate(0,0);
    transition: background-color .5s ease, transform .25s ease, box-shadow .25s ease;
    &:hover, &:focus {
        background-color: lighten($black, 25%);
        transform: translate(0, -5px);
        box-shadow: 0px 6px 5px -4px rgba(0,0,0,0.6);
    }
    &:active {
        background-color: $black;
        box-shadow: 0px 3px 10px -4px rgba(0,0,0,0.4);
        transform: translate(0,0);
    }
}
</style>