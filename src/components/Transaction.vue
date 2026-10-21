<script>

export default {
    props: ['sendComplete'],
    data() {
        return {

        }
    },
    methods: {
        arraytest() {
            console.log(this.sendComplete)
        }
    },


}
</script>

<template>
    <div class="w-full h-fit min-h-screen flex bg-green-100 flex-col items-center py-10 pt-35 pb-30 gap-2">
        
        <div v-for="transact in sendComplete" :key="transact.id"
            class="w-350 h-fit border rounded-xl shadow-lg bg-[#96e788] flex justify-between gap-10 items-center p-5">
            <div class=" w-750 h-fit grid grid-cols-4 space-y-2">
                <div class="">
                    <p class="text-md font-bold">Full Name:</p>
                    <p class="text-md font-semibold ml-1 text-gray-800/70">{{ transact.name }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Email Address:</p>
                    <p class="text-md font-semibold ml-1 text-gray-800/70">{{ transact.email }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Phone Number:</p>
                    <p class="text-md font-semibold ml-1 text-gray-800/70">{{ transact.phone }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Select Services:</p>
                    <p class="text-md font-semibold ml-1 text-gray-800/70">{{ transact.select }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Preffered Doctor:</p>
                    <p class="text-md font-semibold ml-1 text-gray-800/70">{{ transact.doc }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Date:</p>
                    <p class="text-md font-semibold ml-1 text-gray-800/70">{{ transact.mdy }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Time:</p>
                    <p class="text-md font-semibold ml-1 text-gray-800/70">{{ transact.oras }}</p>
                </div>

            </div>
            <div class="  bg-[#146905]/50 w-full h-fit min-h-30 p-5 rounded-md ">
                <p class="text-md font-bold">Message:</p>
                <p class="text-md font-semibold ml-1 text-gray-100/90">{{ transact.message }}</p>
            </div>
        </div>
    </div>
</template>