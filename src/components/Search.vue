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
                <select name="" id="">
                    <option value="volvo">Resturant</option>
                    <option value="saab">Bakery</option>
                    <option value="opel">Cafe</option>
                </select>
            </li>
            <li>
                <input type="text" placeholder="search name...">
            </li>
        </ul>
    </section>
</nav>
</template>

<script>
export default {

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

.menu > ul {
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    flex-direction: row;
    height: 100%;
    align-items: center;
}

.menu > ul > li {
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
