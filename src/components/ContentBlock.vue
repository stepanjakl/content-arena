<template>
    <div class="container mx-auto pt-4 md:pb-24 pb-12">
        <div class="sm:p-8 p-4">

            <!-- IMAGE LEFT -->
            <div v-if="this.left" class="flex xl:flex-row lg:flex-row md:flex-col sm:flex-col flex-col">

                <div v-if="this.left" class="md:pr-16 pr-0 xl:w-7/12 lg:w-7/12 md:w-full sm:w-full w-full">
                    <slot></slot>
                </div>

                <div class="xl:w-5/12 lg:w-5/12 md:w-full sm:w-full w-full relative">
                    <h4 class="font-bold text-sm uppercase pb-4 tracking-widest text-gray-800">{{ this.label }}</h4>
                    <h3 class="font-semibold text-2xl pb-6 text-gray-800">{{ this.header }}</h3>
                    <p class="font-normal text-gray-600 pb-8 leading-relaxed">{{ this.text }}</p>

                    <div v-if="this.btnTwo" class="pt-4">
                        <anim-button blue to="/sellers" class="mr-2">Sellers</anim-button>
                        <anim-button yellow to="/buyers">Buyers</anim-button>
                    </div>

                    <div v-if="this.btnOne" class="pt-4">
                        <anim-button blue :ahref="this.btnLink">Learn more</anim-button>
                    </div>
                </div>
            </div>

            <!-- IMAGE RIGHT -->
            <div v-if="this.right" class="flex xl:flex-row lg:flex-row md:flex-col-reverse sm:flex-col-reverse flex-col-reverse">

                <div class="xl:w-5/12 lg:w-5/12 md:w-full sm:w-full w-full relative">
                    <h4 class="font-bold text-sm uppercase pb-4 tracking-widest text-gray-800">{{ this.label }}</h4>
                    <h3 class="font-semibold text-2xl pb-6 text-gray-800">{{ this.header }}</h3>
                    <p class="font-normal text-gray-600 pb-8 leading-relaxed">{{ this.text }}</p>

                    <div v-if="this.btnTwo" class="pt-4">
                        <anim-button blue to="/sellers" class="mr-2">Sellers</anim-button>
                        <anim-button yellow to="/buyers">Buyers</anim-button>
                    </div>

                    <div v-if="this.btnOne" class="pt-4">
                        <anim-button blue :ahref="this.btnLink">Learn more</anim-button>
                    </div>
                </div>

                <div v-if="this.right" class="md:pl-16 pl-0 md:mb-0 mb-4 xl:w-7/12 lg:w-7/12 md:w-full sm:w-full w-full">
                    <slot></slot>
                </div>
            </div>

        </div>
    </div>
</template>


<script>
    import AnimButton from '@/components/AnimButton'

    export default {
        name: 'HomeReference',
        components: {
            AnimButton
        },
        props: {
            right: Boolean,
            left: Boolean,

            label: String,
            header: String,
            text: String,

            btnTwo: Boolean,

            btnOne: Boolean,
            btnLink: String
        }
    }
</script>

<style scoped>

</style>
