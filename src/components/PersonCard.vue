<template>
    <div class="person-card">
        <div class="photo">
            <!-- <img :src="person.photo" alt="photo" /> -->
            <img src="https://images.pexels.com/photos/3777943/pexels-photo-3777943.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                alt="">
        </div>
        <div class="info">
            <!-- <h2>{{ person.name }}</h2> -->
            <!-- <p class="info-blurb">{{ person.info }}</p> -->
            <h2>JOHN SMITH</h2>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam obcaecati officiis neque minus itaque
                culpa, possimus numquam unde, officia fuga nulla doloribus adipisci iure iusto repudiandae dolore!
                Possimus, est asperiores.</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        person: Object
    }
}
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