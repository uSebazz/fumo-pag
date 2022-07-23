<template>
    <div>
        <section class="flex h-screen text-white items-center justify-center">
            <RefreshIcon class="animate-spin h-12 mr-11" />
            <figure class="flex flex-col text-center w-11/12 gap-6 md:w-auto md:gap-8">
                <h1 class="font-sans font-bold text-5xl md:text-6xl">
                    Loading Fumo Image...
                </h1>
            </figure>
        </section>
    </div>
</template>

<script>
import { RefreshIcon } from '@heroicons/vue/solid'

export default {
    components: {
        RefreshIcon
    }
}
</script>