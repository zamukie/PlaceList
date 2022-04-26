<template>
<main>
    <Search @search="search" :placeList="placeList" />
    <div class="placeContainer">
        <div class="placeList">
            <Card v-for="(placeItem, i) in placeList" :key="i" :placeItem="placeItem" />
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
            placeList: [],
            placeListInnitial: []
        }
    },
    mounted() {
        this.getPlaceData()
    },
    methods: {
        getPlaceData() {
            this.placeList = Json
            this.placeListInnitial = Json
        },
        search(event) {
            this.placeList = this.placeListInnitial.slice().filter(item =>
                item.name.toLowerCase().includes(event.target.value.toLowerCase()) ||
                item.address.toLowerCase().includes(event.target.value.toLowerCase()) ||
                item.categories.some(v => v.toLowerCase() == event.target.value.toLowerCase())
                )
            console.log(this.placeList.slice(), 'test');
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
