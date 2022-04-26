<template>
<nav class="navbar">
    <section class="logo">
        <figure>
            <img src="../assets/ics.jpg" alt="">
        </figure>
    </section>
    <section class="menu">
        <ul>
            <li>
            <li>Sarawut Boonruang</li>
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
.navbar {
  background-color: #134B8A;
  padding: 16px 24px;
  display: flex;
  flex-direction: row;
  color: #FFFF;
}
.logo > figure > img {
  width: 56px;
}
.logo {
  flex: 1;
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
  font-size: 20px;
  margin: 0 12px;
}
.menu > ul > li > img {
    width: 60px;
    border-radius: 56px;
}
</style>
