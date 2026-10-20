<script>
export default {
    props: ['sendForm'],
    data(){
        return{
            
            myId: 0
        }
    },
    methods:{
        backTo(mod){
            this.sendForm.splice(mod, 1)
        },
        toTrans(fullname, emailaddress, phonenum, selectService, doctor, date, time, mess){
            this.$emit('complete', {id: this.myId + 1, name: fullname, email: emailaddress, phone: phonenum, select: selectService, doc: doctor, mdy:date, oras: time, message: mess});
            this.backTo()
        },
        arraytest(){
            console.log(this.sendForm)
        }
    }
}
</script>

<template>
    <div class="w-full h-fit min-h-screen flex flex-col items-center py-10 mt-25 pb-30 gap-10">
        <!-- <button @click="arraytest" class="mt-30">array</button> -->
        <div v-for="(details, index) in sendForm" 
            class="w-350 h-fit border rounded-xl  bg-[#96e788] flex justify-between gap-10 items-center p-5">
            <div class=" w-750 h-fit grid grid-cols-4 space-y-2">
                <div class="">
                    <p class="text-md font-bold">Full Name:</p>
                    <p class="text-md font-semibold ml-1 text-gray-700">{{ details.name }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Email Address:</p>
                    <p class="text-md font-semibold ml-1 text-gray-700">{{ details.email }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Phone Number:</p>
                    <p class="text-md font-semibold ml-1 text-gray-700">{{ details.phone }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Select Services:</p>
                    <p class="text-md font-semibold ml-1 text-gray-700">{{ details.select }}</p>
                    
                </div>
                <div>
                    <p class="text-md font-bold">Preffered Doctor:</p>
                    <p class="text-md font-semibold ml-1 text-gray-700">{{ details.doc }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Date:</p>
                    <p class="text-md font-semibold ml-1 text-gray-700">{{ details.mdy }}</p>
                </div>
                <div>
                    <p class="text-md font-bold">Time:</p>
                    <p class="text-md font-semibold ml-1 text-gray-700">{{ details.oras }}</p>
                </div>
            </div>
            <div class="">
                <div class="  bg-[#146905]/50 w-110 h-fit p-5 rounded-md ">
                    <p class="text-md font-bold">Message:</p>
                    <p class="text-md font-semibold ml-1 text-gray-200">{{ details.message }}</p>
                </div>
                <div class="space-x-2 flex ml-50">
                    <button @click="toTrans(details.name, details.email, details.phone, details.select, details.doc, details.mdy, details.oras, details.message)"
                        class="mt-5 w-40 h-10 bg-[#146905]/90 rounded-full text-gray-100  font-semibold italic">Complete</button>
                    <button @click="backTo(mod)"
                        class="mt-5 px-5 py-2 bg-red-700/90 rounded-full text-gray-100 font-semibold italic">Cancel</button>
                </div>
            </div>
        </div>
    </div>
</template>