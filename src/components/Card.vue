<template>
<section class="placeVertical">
    <section class="placeDescription">
        <div class="image">
            <img :src="placeItem.profile_image_url" alt="">
        </div>
        <div>
            <section class="placename">{{ placeItem.name }}</section>
            <section class="detail">
                <div class="open">{{ placeItem.categories }}</div>
                <div class="rating">{{ placeItem.rating }}</div>
            </section>
        </div>
    </section>
    <section class="placeImage">
        <!-- <img :src="placeItem.images" alt=""> -->
    </section>
</section>
</template>

<script>
export default {
    props: [ 'placeItem' ],
}
</script>

<style scoped>
.placeVertical {
    box-shadow: 0px 0px 12px gainsboro;
    border-top-left-radius: 16px;
    border-top-right-radius: 16px;
    border-top-right-radius: 16px;
    display: flex;
    flex-direction: column;
}

.placeVertical:hover {
    transition: all 0.3s ease-in-out;
    box-shadow: 0px 0px 32px #CCC;
}

.placeVertical .placeImage img {
    width: 100%;
    height: 240px;
    object-fit: cover;
    border-radius: 16px;
}
.placeVertical .placeDescription {
    padding: 16px 18px;
    padding-top: 12px;
    flex: 1;
    display: flex;
    flex-direction: row;
}
.placeVertical .placeDescription .image img {
    width: 70px;
    height: 100%;
     display: flex;
    /* flex-direction: column;
    justify-content: flex-end; */
    flex-direction: row;
    align-items: flex-start;
}
.placeVertical .placename {
    margin-left: 10px;
    font-weight: bold;
    color: red;
    font-size: 1.2rem;
}
.placeVertical .detail {
    margin-left: 10px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}
.detail .open {
    color: blue;
}
.detail .rating {
    color: blueviolet;
    margin-left: 10px;
}
</style>
