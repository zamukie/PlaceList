<template>
<main>
    <Search />
    <div class="placeContainer">
        <div class="placeList">
            <Card />
            <Card />
            <Card />
        </div>
    </div>
</main>
</template>

<script>
import Card from '../components/Card.vue'
import Search from '../components/Search.vue'
import Json from '../example_data.json'
export default {
    components: {
        Card,
        Search
    },
    data() {
        return {
            placeList: []
        }
    },
    mounted() {
        this.getPlaceData()
    },
    methods: {
        getPlaceData() {
            this.placeList = Json
            for (let i = 0; i < this.placeList.length; i++) {
                console.log(this.placeList[i]);
            }
        }
    }
}
</script>

<style scoped>
.placeContainer {
    padding: 40px;
}

.placeList {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-row-gap: 40px;
    grid-column-gap: 24px;
    margin-top: 20px;
}

.text {
    font-size: 50px;
    font-weight: bold;
    margin-left: 30px;
    margin-top: 20px;
}

.Head {
    padding: 16px 24px;
    display: flex;
    flex-direction: row;
    color: #000;
}

.Head .text {
    flex: 1;
}

.Head .menu {
    /* flex: 1; */
    margin: 0;
    padding: 0;
    list-style: none;
    flex-direction: row;
    height: 100%;
    align-items: center;
}
</style>
