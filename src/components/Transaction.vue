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
    <div class="w-full h-fit min-h-screen flex flex-col items-center py-10 mt-25 pb-30 gap-2">
        
        <div v-for="transact in sendComplete" :key="transact.id"
            class="w-350 h-fit border rounded-xl  bg-[#96e788] flex justify-between gap-10 items-center p-5">
            <div class=" w-750 h-fit grid grid-cols-4 space-y-2">
                <div class="">
                    <p class="text-md font-bold">Full Name:</p>
                    <p class="text-md font-semibold ml-1 text-gray-600">{{ transact.name }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Email Address:</p>
                    <p class="text-md font-semibold ml-1 text-gray-100">{{ transact.email }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Phone Number:</p>
                    <p class="text-md font-semibold ml-1 text-gray-100">{{ transact.phone }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Select Services:</p>
                    <p class="text-md font-semibold ml-1 text-gray-100">{{ transact.select }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Preffered Doctor:</p>
                    <p class="text-md font-semibold ml-1 text-gray-100">{{ transact.doc }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Date:</p>
                    <p class="text-md font-semibold ml-1 text-gray-100">{{ transact.mdy }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Time:</p>
                    <p class="text-md font-semibold ml-1 text-gray-100">{{ transact.oras }}</p>
                </div>

            </div>
            <div class="  bg-[#146905]/50 w-full h-20 p-5 rounded-md ">
                <p class="text-md font-bold">Message:</p>
                <p class="text-md font-semibold ml-1 text-gray-100">{{ transact.message }}</p>
            </div>
        </div>
    </div>
</template>