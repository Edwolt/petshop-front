<template>
    <div class='petData'>
        <Data class='profile-pic'>
            <transition name='fade'>
                <img v-if='images[type]' :src='require(`@/assets/${images[type].src}`)' alt="profilePic">
                <img v-else src='@/assets/biscuit.png' >
            </transition>
        </Data>
        <Data class='data' label='Name'>{{ name }}</Data>
        <Data class='data' label='Type'>{{ capitalize(type) }}</Data>
        <Data class='data' label='Race'>{{ race }}</Data>
        <Data class='data' label='Age'>{{ age }}</Data>
    </div>
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
    name: 'Pet',
    components: {
        Data
    },
    props: ['name', 'type', 'race', 'age'],
    data: () => ({
        images
    }),
    methods: {
        capitalize: str => (
            typeof (str) === 'string' ?
            str.charAt(0).toUpperCase() + str.slice(1) :
            ''
        )
    }
}
</script>

<style scoped>
.petData *{
  margin: 10px;
  padding: 5px;
}
.petData img{
  max-width: 200px;
  max-height: 200px;
}


/* Reducing the space between the label and the data */
.petData .data ::v-deep h3{
    margin-right: 0px;
}
.petData .data ::v-deep p{
    margin-left: 0px;
}


.petData button{
  background: var(--secondarycolor);
  width: 100%;
  border: none;
  border-radius: 1px;
  color: white;
  font-size: 20px;
  font-weight: 500;
  cursor: pointer;
}
.petData button:hover{
  filter: brightness(1.2);
}
</style>