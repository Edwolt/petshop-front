<template>
     <div class='card' :class='{lefty: lefty, flex: flex}'>
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: [
        'lefty',
        'flex'
    ]
}
</script>

<style scoped>
.card{
    background: var(--cardcolor);
    max-width: 80vw;
    text-align: center;
    padding: 25px;
    font-size: 20px;
    box-shadow: 2px 2px 10px rgba(0,0,0,0.3);
    margin-bottom: 25px;
    border-radius: 10px;
}

.lefty{
    margin-left: 50px;
}
.flex{
    display: flex;
    align-items: stretch;
    justify-content: flex-start;
    flex-wrap: wrap;
}

.card h1{
    margin: 10px 0px 15px 0px;
    color: rgb(37, 0, 248);
}

.card img{
    height: 300px;
}

a{
    color: inherit;
    text-decoration: none;
}
a:visited{
    color: inherit;
    text-decoration: none;
}


.link{
    text-decoration: underline;
}
@media (max-width: 500px){
    .card img{
        height: 200px;
    }
}
</style>