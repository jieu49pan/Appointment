<script>
export default {
    data() {
        return {
            fullname: '',
            emailaddress: '',
            phonenum: '',
            doctor: '',
            date: '',
            time: '',
            mess: '',
            selectService: '',
            mental: 'Mental Health',
            general: 'General Medicine',
            physical: 'Physical Therapy',
            myId: 0

        }
    },
    methods: {
        backTo(mod) {
            this.$emit('modal', mod);
            console.log(mod)
        },
        submitNa() {
            this.$emit('send-to', {
                id: this.myId,
                name: this.fullname,
                email: this.emailaddress,
                phone: this.phonenum,
                select: this.selectService,
                doc: this.doctor,
                mdy: this.date,
                oras: this.time,
                message: this.mess
            });
            
            this.backTo()
        }

    }
}
</script>

<template class="">

    <div class="w-full  h-screen flex justify-center items-center fixed top-0 backdrop-blur-md z-999 bg-gray-900/50">
        <div class="w-200 h-fit bg-[#A9EB9E]/80 p-10 rounded-xl">
            <input v-model="fullname" type="text"
                class="w-full h-15  bg-[#146905]/70 rounded-md italic px-5 text-gray-100" placeholder="Full Name">
            <div class="w-full grid grid-rows-3 grid-cols-2 gap-5 mt-5">
                <input v-model="emailaddress" type="text"
                    class="w-full h-15  bg-[#146905]/70 italic rounded-md px-5 text-gray-100"
                    placeholder="Email Address" name="" id="">
                <input v-model="phonenum" type="text"
                    class="w-full h-15  bg-[#146905]/70 italic rounded-md px-5 text-gray-100" placeholder="Phone Number"
                    name="" id="">

                <select v-model="selectService"
                    class="w-full h-15  bg-[#146905]/60 italic rounded-md px-5 text-gray-100"
                    placeholder="Select Services" name="" id="">
                    <option class="text-[#146905]/28" value="">Select Services</option>
                    <option value="Mental">Mental Health</option>
                    <option value="General">General Medicine</option>
                    <option value="Physical">Physical Therapy</option>
                </select>
                <input v-model="doctor" type="text"
                    class="w-full h-15  bg-[#146905]/70 italic rounded-md px-5 text-gray-100"
                    placeholder="Preffered Doctor" name="" id="">
                <input v-model="date" type="date"
                    class="w-full h-15  bg-[#146905]/70 italic rounded-md px-5 text-gray-100" placeholder="MM/DD/YYYY">
                <input v-model="time" type="time"
                    class="w-full h-15  bg-[#146905]/70 italic rounded-md px-5 text-gray-100" placeholder="Time" name=""
                    id="">
            </div>
            <textarea v-model="mess" name="" id=""
                class="w-full h-60  bg-[#146905]/70  rounded-md mt-5 italic p-5 text-gray-100"
                placeholder="Message"></textarea>
            <div class="flex gap-5">

                <button @click="submitNa"
                    class="mt-5 w-30 h-10 bg-[#146905]/90 rounded-full text-gray-100  font-semibold italic">Submit</button>
                <button @click="backTo(false)"
                    class="mt-5 px-5 py-2 bg-red-700/90 rounded-full text-gray-100 font-semibold italic">Close</button>
            </div>

        </div>
    </div>
</template>