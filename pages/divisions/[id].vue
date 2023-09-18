<template>
    <div>
        <Navbar />
        <div class="w-6/12 mx-auto">
            <p>Division Id: {{ id }}</p>
            <div v-for="(info, ind) in infos" :key="ind">
                <div v-if="info._id == id">
                    <p>Division: {{ info._id }}</p>
                    <img :src="info.imageUrl" alt="" class="w-full h-fit">
                    <p>{{ info.description }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
const route = useRoute();
const { id }: { id: number }  = route.params;
// const { id } = useRoute().params
const infos: {name: string, _id: number, imageUrl: string, description: string} [] = [
    {
        name: "Rajshahi",
        imageUrl: "https://images.prothomalo.com/prothomalo-english%2Fimport%2Fmedia%2F2016%2F08%2F05%2Fd98ab9fa431efd2c269545949b589ce3-rajshahi.png?rect=0%2C0%2C1200%2C675&auto=format%2Ccompress&fmt=webp&dpr=1.0&format=webp&w=480",
        description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dignissimos fugiat voluptates cum totam, nihil hic quia. Natus molestiae nulla saepe!",
        _id: 1
    },
    {
        name: "Cumilla",
        imageUrl: "https://images.prothomalo.com/prothomalo-english%2Fimport%2Fmedia%2F2016%2F08%2F05%2Fd012bb6fb93e2a7a9f47d3e6955a6659-comilla.png?auto=format&fit=fill&bg=000000&q=35&w=1200",
        description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dignissimos fugiat voluptates cum totam, nihil hic quia. Natus molestiae nulla saepe!",
        _id: 2
    },
    {
        name: "Chittagong",
        imageUrl: "https://images.prothomalo.com/prothomalo-english%2Fimport%2Fmedia%2F2016%2F08%2F14%2Fd19988b26cd67072298693a8266ab7c7-chattagong.gif?auto=format%2Ccompress&w=400&dpr=2.6",
        description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dignissimos fugiat voluptates cum totam, nihil hic quia. Natus molestiae nulla saepe!",
        _id: 3
    },
    {
        name: "Khulna",
        imageUrl: "https://images.prothomalo.com/prothomalo-english/import/media/2016/08/05/05ad963be0d6da2e81aa7887b76a7fda-khulna.png?w=1200&h=675",
        description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dignissimos fugiat voluptates cum totam, nihil hic quia. Natus molestiae nulla saepe!",
        _id: 4
    },
    {
        name: "Mymensingh",
        imageUrl: "https://qph.cf2.quoracdn.net/main-qimg-bb55f0fd381565d9bf8b1c5963585e62-lq",
        description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dignissimos fugiat voluptates cum totam, nihil hic quia. Natus molestiae nulla saepe!",
        _id: 5
    },
    {
        name: "Rangpur",
        imageUrl: "https://images.prothomalo.com/prothomalo-english%2Fimport%2Fmedia%2F2016%2F09%2F12%2F89fd32333c8382f1d97344411a65e951-rongpur.png?auto=format&q=35&w=1200&rect=0,0,1200,675",
        description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dignissimos fugiat voluptates cum totam, nihil hic quia. Natus molestiae nulla saepe!",
        _id: 6
    }
]
</script>

<style scoped>

</style>