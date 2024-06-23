<template>
 <h1>Welcome to the Vue.js Power Hour!</h1>
 <div class="griddy">
 <img src="../assets/codemom.png"/>
 <div class="texty">
    <h2>Tori Brenneison</h2>
    <h2>AKA "Code Mom"</h2>
    <h3>About Me</h3>
    <ul>
    <li><i class="fa-regular fa-compass pad-right"></i>Cleveland, OH, USA</li>
    <li><i class="fa-regular fa-building pad-right"></i>Software Developer IV @ Medical Mutual</li>
    </ul>
    <h3>Contact Info</h3>
    <ul>
    <li><i class="fa-brands fa-twitter pad-right"></i>@not_unambitious</li>
    <li><i class="fa-brands fa-instagram pad-right"></i>@your.code.mom</li>
    <li><i class="fa-brands fa-github pad-right"></i>tbrenneison</li>
    <li><i class="fa-brands fa-linkedin pad-right"></i>toribrenneison</li>
    <li><i class="fa-regular fa-envelope pad-right"></i>tori.brenneison@gmail.com</li>

</ul>
</div>
</div>

</template>

 
<script>
 
</script>
 
<style>
 h1 { 
    font-size: 300%;
 }

 img { 
    width: 90%;
 }

 .griddy { 
    margin-top: 25px;
    display: grid; 
    grid-template-columns: 1fr 1fr;
    grid-template-areas: 'image list';
 }

 .texty { 
    grid-area: 'list';
    font-size: 150%;
 }

 li { 
    list-style-type: none;
 }

 .pad-right { 
    padding-right: 5px;
 }

 
</style>