<template>


    <div class="">
        <h1 class=" text-gray-900 font-bold text-6xl text-[32px]">Openheimer</h1>
        <div class="mt-11 flex flex-row justify-between item-center">
            <div class="flex flex-col space-y-3">
                <div class="text-gray-700 text-base-bold font-bold uppercase">Director</div>
                <p class="text-gray-700 text-base-bold text-xl font-semibold ">Christopher Nolan</p>
            </div>

            <div class="flex flex-col space-y-3">
                <div class="text-gray-700 text-base-bold font-bold uppercase">Release Date</div>
                <p class="text-gray-700 text-base-bold text-xl font-semibold ">21 July 2024</p>
            </div>
        </div>
        <div v-if="currentStep == 0">
            <div class="max-w-full mx-12">
                <div class=" p-2 mt-7 bg-white shadow-2xl">


                    <img src="data:image/jpeg;base64,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"
                        alt="poster image" />
                </div>
                <div class="flex item-center justify-center mt-7">
                    <Button size="xl" variant="solid" @click="currentStep++"> Book Ticket</Button>
                </div>
                <div class="flex flex-col space-y-3 mt-4">
                    <h2 class="text-grey-700 font-bold uppercase ">Synopsis</h2>
                    <p class="text=gray-600 text-lg font-normal ">Lorem ipsum dolor sit amet consectetur, adipisicing
                        elit.
                        Dolor velit unde sit quia nam sunt dignissimos aspernatur nemo soluta, eum consequatur illo,
                        quae,
                        totam
                        delectus magni dolore repellat! Modi, placeat.</p>
                </div>
            </div>

        </div>


        <div v-else-if="currentStep == 1">
            <h2 class="font-medium text-xl mt-7 text-gray-900">How many Seats?</h2>
            <div class="flex flex-col space-y-5 ">
                <Button @click="setNumerofSeats(index)" size="lg"
                    :variant="index === bookingData.numberOfSeats ? 'subtle' : 'white'" class=" shadow-lg mt-6"
                    v-for="(index) in 8">{{ index }}</Button>
            </div>

        </div>

        <!-- 3rd page -->

        <div v-else-if="currentStep == 2">
            <div class="flex flex-col space-y-4 max-w-sm ">
                <h2 class="font-medium text-xl mt-7 text-gray-900">Date</h2>
                <Input type="date" value="today" w-model="bookingData.date" />
            </div>
            <div class="flex flex-col space-y-4 max-w-sm">
                <h2 class="font-medium text-xl mt-7 text-gray-900">Cinema & Show</h2>
                <div class="space-y-2">
                    <div class=" bg-white shadow-xl p-4 rounded  flex flex-col space-y-4">
                        <h3 class="text-sm font-bold text-gray-800">Star Talkies</h3>
                        <div class="flex flex-row space-x-2">
                            <Button size="sm" variant="outline">12:30PM</Button>
                            <Button size="sm" variant="outline">03:30PM</Button>
                        </div>
                    </div>
                    <div class=" bg-white shadow-xl p-4 rounded  flex flex-col space-y-4">
                        <h3 class="text-sm font-bold text-gray-800">Anupama Theater</h3>
                        <div class="flex flex-row space-x-2">
                            <Button size="sm" variant="outline">11:10AM</Button>
                            <Button size="sm" variant="outline">01:30PM</Button>
                        </div>
                    </div>

                </div>
            </div>


        </div>

        <div class="flex flex-row mt-6 space-x-2 item-center space-between justify-center">
            <Button size="xl" v-if="currentStep !== 0" variant="solid" @click="currentStep++"> Next</Button>
            <!-- class=" mt-5" size="lg" -->
            <Button size="xl" v-if="currentStep !== 0" variant="subtle" @click="currentStep--">Go
                Back</Button>

        </div>


    </div>
</template>
<script setup>
import { ref, reactive } from 'vue'
const currentStep = ref(0)

const today = new Date().toISOString().substr(0, 10);

const bookingData = reactive({
    numberOfSeats: 0,
    seat: [],
    date: today
})
function setNumerofSeats(n) {
    bookingData.numberOfSeats = n
}
</script>
export default MovieDetail
