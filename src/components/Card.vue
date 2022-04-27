<template>
<section class="placeVertical">
    <section class="placeDescription">
        <div class="image">
            <img :src="placeItem.profile_image_url" alt="">
        </div>
        <div class="data">
            <section class="placename">{{ placeItem.name }}</section>
            <section class="detail">
                <div class="open">
                    {{ placeItem.operation_time[day].time_open }} AM -
                    {{ placeItem.operation_time[day].time_close }} PM
                </div>
                <div class="rating">● {{ placeItem.rating }}</div>
            </section>
        </div>
    </section>
    <section class="placeImage">
        <img class="pic1" :src="placeItem.images[0]" alt="">
        <img :src="placeItem.images[1]" alt="">
        <img class="pic3" :src="placeItem.images[2]" alt="">
    </section>
</section>
</template>

<script>
import moment from 'moment'
export default {
    props: ['placeItem'],
    data() {
        return {
            day: moment().day() - 1
        }
    },
}
</script>

<style scoped>
.placeVertical {
    box-shadow: 0px 0px 12px gainsboro;
    border-radius: 16px;
    display: flex;
    flex-direction: column;
}

.placeVertical:hover {
    transition: all 0.3s ease-in-out;
    box-shadow: 0px 0px 32px #CCC;
}

.placeVertical .placeImage {
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin-bottom: 20px;
}

.placeVertical .placeImage img {
    width: 30%;
    height: 240px;
    object-fit: cover;
    /* border-radius: 16px; */
}

.placeImage .pic1 {
    border-top-left-radius: 16px;
    border-bottom-left-radius: 16px;
}

.placeImage .pic3 {
    border-top-right-radius: 16px;
    border-bottom-right-radius: 16px;
}

.placeVertical .placeDescription {
    display: flex;
    flex-direction: row;
}

.placeVertical .placeDescription .image {
    padding: 16px 18px;
    padding-top: 12px;
    margin-left: 10px;
}

.placeVertical .placeDescription .data {
    flex: 1;
    /* padding: 16px 18px; */
    padding-right: 20px;
    padding-top: 12px;
}

.placeVertical .placeDescription .image img {
    object-fit: cover;
    border-radius: 10px;
    width: 80px;
    height: 80px;
    display: flex;
    /* flex-direction: column;
    justify-content: flex-end; */
    flex-direction: row;
    align-items: flex-start;
}

.placeVertical .placename {
    margin-left: 10px;
    font-weight: bold;
    color: #000;
    font-size: 36px;
}

.placeVertical .detail {
    margin-left: 10px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.detail .open {
    color: #000;
}

.detail .rating {
    color: #134b8a;
    font-weight: bold;
    font-size: 20px;
}
</style>
