<script>
export default {
    data() {
        return {

        }
    },
    methods: {
        buttonBook(modal){
            this.$emit('showModal', modal)
        },
        Navi(page){
            this.$emit('goTo', page)
        }
        
    }
}
</script>

<template class="">
    <nav>
        <div class="bg-[#7B9376]/50 w-full h-30 fixed top-0 z-30  flex justify-between items-center px-15 backdrop-blur-xs">
            <img class="w-50" src="https://unifato.com/curevo/images/logo.svg" alt="">
            <div class="space-x-5">
                <button @click="Navi('Home')" class="bg-[#7CC46F] w-40 h-11 rounded-lg text-white font-semibold italic hover:scale-105 duration-300">Home</button>
                <button @click="Navi('Booking')" class="bg-[#7CC46F] w-40 h-11 rounded-lg text-white font-semibold italic hover:scale-105 duration-300">Appointment</button>
                <button @click="Navi('Transaction')" class="bg-[#7CC46F] w-40 h-11 rounded-lg text-white font-semibold italic hover:scale-105 duration-300">Transaction</button>
            </div>
            <button @click="buttonBook(true)" class="bg-[#7CC46F] w-40 h-11 rounded-lg text-white font-semibold italic hover:scale-105 duration-300">Book</button>
        </div>
    </nav>

</template>