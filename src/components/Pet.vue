<template>
    <Card class='changeDim' lefty='true'>
        <div class='petCard'>
            <transition name="fade" mode='out-in'>
                <PetData :name='name' :type='type' :race='race' :age='age' v-if='!edit'></PetData>
                <PetForm v-if='edit'></PetForm>
            </transition>
            <button @click='onClick'>{{ this.edit ? 'Confirm' : 'Edit' }} </button>
        </div>
    </Card>
</template>

<script>
import PetForm from '@/components/PetForm'
import PetData from '@/components/PetData'
import Card from '@/components/Card'

export default {
    components: {
        Card,
        PetForm,
        PetData
    },
    props: ['name', 'type', 'race', 'age'],
    data: () => ({
        edit: false
    }),
    methods: {
        onClick() {
            this.edit = !this.edit
        }
    }
}
</script>

<style scoped>
.changeDim{
    height: 80vh;
    width:  45vw;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .3s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active em versões anteriores a 2.1.8 */ {
  opacity: 0;
}

.petCard{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}

.petCard *{
  margin: 10px;
  padding: 5px;
}

/* Reducing the space between the label and the data */
.petCard .data ::v-deep h3{
    margin-right: 0px;
}
.petCard .data ::v-deep p{
    margin-left: 0px;
}

.petCard button{
  background: var(--secondarycolor);
  width: 100%;
  border: none;
  border-radius: 1px;
  color: white;
  font-size: 20px;
  font-weight: 500;
  cursor: pointer;
}
.petCard button:hover{
  filter: brightness(1.2);
}
</style>