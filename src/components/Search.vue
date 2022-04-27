<template>
<nav class="search">
    <section class="headLine">
        <div class="text">
            <span>Place List</span>
        </div>
    </section>
    <section class="menu">
        <ul>
            <li>
                <select @test="test($event)" v-model="selected">
                    <option disabled value="">Please select one</option>
                    <option value="restaurant">Resturant</option>
                    <option value="bakery">Bakery</option>
                    <option value="cafe">Cafe</option>
                </select>
            </li>
            <li>
                <input @input="find($event)" v-model="search" type="text" placeholder="search name...">
            </li>
        </ul>
    </section>
</nav>
</template>

<script>
export default {
    props: ['placeList'],
    data() {
        return {
            search: '',
            selected: ''
        }
    },
    methods: {
        find(event) {
            this.$emit('search',event)
        },
        test(event) {
            this.$emit('catagories', event)
        }
    }
}
</script>

<style>
figure {
    margin: 0;
}

.search {
    padding: 16px 24px;
    display: flex;
    flex-direction: row;
    color: #000;
}

.headLine {
    flex: 1;
}

.headLine .text {
    font-size: 50px;
    font-weight: bold;
    margin-left: 30px;
    margin-top: 20px;
}

.menu>ul {
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    flex-direction: row;
    height: 100%;
    align-items: center;
}

.menu>ul>li {
    margin: 0 20px;
}

.menu select {
    font-size: 20px;
    width: 100%;
    border-radius: 50px;
    padding: 4px 12px;
    color: rgba(0, 0, 0, .70);
    border: 1px solid #134b8a;
    transition: .15s all ease-in-out;
    background: white;
}

.menu select:focus {
    outline: none;
    transform: scale(1.05);
}

.menu input {
    font-size: 20px;
    width: 100%;
    border-radius: 50px;
    padding: 4px 12px;
    color: rgba(0, 0, 0, .70);
    border: 1px solid #134b8a;
    transition: .15s all ease-in-out;
    background: white;
}

.menu input:focus {
    outline: none;
    transform: scale(1.05);
}
</style>
