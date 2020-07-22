<template>
    <form class='petForm'>
        <Data class='profile-pic'>
            <img v-if='images[type]' :src='require(`@/assets/${images[type].src}`)' alt="profilePic">
            <img v-else src='@/assets/biscuit.png' >
        </Data>
        <Data label='Pet name' class='inputwrpa'>
            <input type='text' name='name' placeholder='Ex.: Rex'>
        </Data>
        <Data label='Type' class='inputwrpa'>
            <select name='type'>
                <option value='' selected>Type</option>
                <option value='dog'>Dog</option>
                <option value='cat'>Cat</option>
                <option value='bird'>Bird</option>
                <!-- <option value='snake'>Snake</option> -->
                <option value='fish'>Fish</option>
                <!-- <option value='rabbit'>Rabbit</option> -->
                <!-- <option value='ramster'>Ramster</option> -->
                <option value='other'>Other...</option>
            </select>
        </Data>
        <Data label='Race' class='inputwrpa'>
            <input type='text' name='name' placeholder='Ex.: Rex'>
        </Data>
        <Data label='Age' class='inputwrpa'>
            <input type='number' name='age' placeholder='5'>
        </Data>
    </form>
</template>

<script>
import Data from '@/components/Data'

const images = {
    dog: {src: 'doggy.png', alt:'pic'},
    cat: {src: 'cat.png', alt:'pic'},
    bird: {src: 'bird.png', alt:'pic'},
    fish: {src: 'fish.png', alt:'pic'}
}

export default {
    name: 'ProfileForm',
    props: ['submit', 'mismatch'],
    components: {
        Data,
    },
    data: ()=> ({
        images,
        type:'others'
    })
}
</script>

<style scoped>
.petForm *{
  padding: 5px;
}
.petForm img{
  max-width: 200px;
  max-height: 200px;
}


.petForm{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
}

.petForm input{
    background-color: none;
    max-width: 40%;
    border: none;
    border-radius: 3px;
    border-bottom: 5px solid purple;
    transition: 0.2s ease;
}
.petForm input:focus{
    border-bottom: 5px solid greenyellow;
}

.inputwrap{
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
}
</style>