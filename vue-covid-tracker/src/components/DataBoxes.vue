<template>
    <div class="grid md:grid-cols-2 gap-4">
        <!-- Box -->
        <div class="shadow-md bg-blue-100 p-10 text-center rounded">
            <h3 class="text-blue-900 font-bold text-3xl mb-4">Cases</h3>
            <div class="text-2xl mb-4">
                <span class="font-bold">New:</span>
                {{numb(stats.NewConfirmed)}}
            </div>
            <div class="text-2xl mb-4">
                <span class="font-bold">Total:</span>
                {{numb(stats.TotalConfirmed)}}
            </div>
        </div>
        <!-- Box -->
        <div class="shadow-md bg-blue-200 p-10 text-center rounded">
            <h3 class="text-blue-900 font-bold text-3xl mb-4">Deaths</h3>
            <div class="text-2xl mb-4">
                <span class="font-bold">New:</span>
                {{numb(stats.NewDeaths)}}
            </div>
            <div class="text-2xl mb-4">
                <span class="font-bold">Total:</span>
                {{numb(stats.TotalDeaths)}}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'DataBoxes',
    props: ['stats'],
    methods: {
        numb(x) {
            return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')
        }
    }
}
</script>