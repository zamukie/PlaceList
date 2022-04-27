<template>
<main>
    <Search @catagories="catagories" @search="search" :placeList="paginatedItems" />
    <div class="placeContainer">
        <div class="placeList">
            <Card v-for="(placeItem, i) in paginatedItems" :key="i" :placeItem="placeItem" />
        </div>
        <div class="mt-3">
            <h6>Default Pills</h6>
            <b-pagination @change="onPageChanged" :per-page="perPage" v-model="currentPage" pills :total-rows="totalRows"></b-pagination>
        </div>
        <!-- <div class="pagination">
            <PaginationButton 
                v-for="page in totalPage" :key="page" 
                @click="updatePageNumber(page)" 
                :text="page"
                :class="{ 'active': page === pageNumber }"
                />
        </div> -->
    </div>
</main>
</template>

<script>
import Card from '../components/Card.vue'
import Search from '../components/Search.vue'
// import PaginationButton from '../components/PaginationButton.vue'
import Json from '../example_data.json'
export default {
    components: {
        Card,
        Search,
        // PaginationButton
    },
    data() {
        return {
            placeList: [],
            placeListInnitial: [],
            paginatedItems: [],
            currentPage: 1,
            perPage: 9,
            totalRows: 0
        }
    },

    watch: {
        pageNumber() {
            this.getPlaceData()
        }
    },

    mounted() {
        this.getPlaceData()
        this.paginate(this.perPage, 0);
    },

    computed: {
        totalPage() {
            return this.row > 0 ? Math.floor(this.row / this.limit) : 0
        }
    },

    methods: {
        getPlaceData() {
            this.placeList = Json
            this.placeListInnitial = Json
            this.paginatedItems = Json
            this.totalRows = Json.length
            // this.total = Json.length
            console.log('total', this.total);
        },
        search(event) {
            let searchResult = this.placeListInnitial.slice().filter(item =>
                item.name.toLowerCase().includes(event.target.value.toLowerCase())
                // || item.categories.some(v => v.toLowerCase() == event.target.value.toLowerCase())
            )
            this.totalRows = searchResult.length
            // this.paginatedItems = searchResult
            this.paginate(this.perPage, 0, searchResult)
        },
        catagories(event) {
            console.log('sss', event);
            this.placeList = this.placeList.slice().filter(item => item.catagories)
        },
        updatePageNumber(page) {
            this.pageNumber = page
            this.getPlaceData()
        },
        paginate(page_size, page_number, page_list) {
            let itemsToParse = page_list?page_list: this.placeList;
            this.paginatedItems = itemsToParse.slice(
                page_number * page_size,
                (page_number + 1) * page_size
            );
        },
        onPageChanged(page) {
            this.paginate(this.perPage, page - 1);
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

.pagination {
    display: flex;
    justify-content: center;
    padding: 0 0 56px;
}

.pagination button {
    width: 40px;
    height: 40px;
    border-radius: 100%;
    margin: 0 4px;
}

.pagination button.active {
    background-color: #134b8a;
    border: 1px solid #fff;
    color: #FFF;
    font-weight: bold;
}
</style>
