<template>
    <div class="w-full h-[80vh] flex justify-center items-center">
        <h1 class="text-gray-900 text-center flex flex-col gap-6 leading-12 text-6xl md:text-7xl lg:text-11xl 2xl:text-10xl 3xl:text-13xl font-bold">
            <span>&nbsp;a design</span>
            <span>agency with</span>
            <span class="w-screen">
                <div className="hidden sm:block overflow-hidden my-4">
                    <div className="flex flex-row inline-block animate-marquee">
                    <!-- <div class="bg-gray-800 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">experience</div>
                    <div class="bg-gray-800 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">experience</div>
                    <div class="bg-gray-800 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">experience</div>
                    <div class="bg-gray-800 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">experience</div> -->
                    <div
                            v-for="index in numberOfDivs"
                            :key="index"
                            class="bg-gray-900 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3"
                        >
                            experience
                        </div>
                </div>
                </div>

                <div className="sm:hidden overflow-hidden my-4">
                    <div className="flex flex-row inline-block animate-marquee">
                    <!-- <div class="bg-gray-800 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">experience</div>
                    <div class="bg-gray-800 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">experience</div>
                    <div class="bg-gray-800 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">experience</div>
                    <div class="bg-gray-800 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">experience</div> -->
                    <div class="bg-gray-900 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">
                            experience
                        </div>
                        <div class="bg-gray-900 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">
                            experience
                        </div>
                        <div class="bg-gray-900 text-gray-100 pb-7 px-8 rounded-full flex justify-center items-center mr-3">
                            experience
                        </div>
                </div>
                </div>
            </span>
      
        </h1>
    </div>
</template>

<script>
export default {
    data() {
        return {
            // Number of divs to create based on screen width
            numberOfDivs: 0
        };
    },
    mounted() {
        // Call the function to calculate the number of divs
        this.calculateNumberOfDivs();
        // Listen for window resize events to recalculate the number of divs
        window.addEventListener('resize', this.calculateNumberOfDivs);
    },
    beforeMount() {
        // Remove the resize event listener to prevent memory leaks
        window.removeEventListener('resize', this.calculateNumberOfDivs);
    },
    methods: {
        calculateNumberOfDivs() {
            // Get the width of the screen
            const screenWidth = window.innerWidth;
            // Get the width of each experience div
            const divWidth = 200; // You can adjust this value according to your design
            // Calculate the number of divs based on the screen width and div width
            this.numberOfDivs = Math.floor(screenWidth / divWidth);
        }
    }
};
</script>
