<template>
    <h1>Hi world.</h1>
    <div>
        <SignUp></SignUp>
    </div>
    
    <div class="tele">
        <h2>Tele</h2>
        <div id="sup"></div>
    </div>
    
    <button @click="open1 = true;open2 = true;">Открыть модальное окно</button>
    <Teleport to="body">
        <div v-if="open1" class="modal">
            <p>Привет из модального окна1!</p>
            <button @click="open1 = false">Закрыть1</button>
        </div>
    </Teleport>
    <Teleport  
        defer
        to="#sup"
    >
        <div v-if="open2" class="modal">
            <p>Привет из модального окна2!</p>
            <button @click="open2 = false">Закрыть2</button>
        </div>
    </Teleport>
</template>

<script setup>
    import SignUp from '@/components/auth/SignUp.vue';
    import { ref } from 'vue';
    
    const open1 = ref(false);
    const open2 = ref(false);
</script>

<style scoped>
.modal{
  /* position: fixed;
  z-index: 999; */
  /* top: 20%;
  left: 50%; */
  width: 300px;
  background-color: gray;
  padding: 1rem;
  /* margin-left: -150px; */
}
.tele{
    padding: 1rem;
    background-color: darkkhaki;
}
</style>
