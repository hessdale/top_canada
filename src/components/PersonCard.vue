<template>
    <div class="person-card">
        <img :src="person.photo" :alt="person.name" class="person-photo" />
        <h3 class="person-name">{{ person.name }}</h3>
        <p class="person-networth">Net Worth: {{ person.netWorth }}</p>
        <p class="person-media">Media Influence: {{ person.mediaInfluence }}</p>
        <p class="person-controversies">Controversies: {{ person.controversies }}</p>
    </div>
</template>

<script>
export default {
    props: {
        person: {
            type: Object,
            required: true,
        },
    },
};
</script>

<style scoped>
.person-card {
    display: flex;
    border: 1px solid black;
    margin-bottom: 10px;
    padding: 10px;
}

.photo img {
    max-width: 100px;
    max-height: 100px;
    margin-right: 20px;
}

.info h2 {
    font-weight: bold;
    text-transform: uppercase;
    margin: 0;
}

.info-blurb {
    font-size: 0.9em;
}
</style>