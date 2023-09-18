<template>
    <div>
        <Navbar />
        <div class="w-6/12 mx-auto">
            <p>Division Id: {{ id }}</p>
            <div v-for="(restaurant, ind) in restaurants" :key="ind">
                <div v-if="restaurant._id == id">
                    <p>Division: {{ restaurant._id }}</p>
                    <img :src="restaurant.imageUrl" alt="" class="w-full h-fit">
                    <p>{{ restaurant.description }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
// import { useRouter } from 'vue-router'
    export default {
        data() {
            return {
                category: '',
                router:  {} as object,
                restaurants: [
                    {
                        name: "Roshona Bilas",
                        imageUrl: "https://mir-s3-cdn-cf.behance.net/projects/404/abe989103327839.Y3JvcCwzMTQ3LDI0NjEsMCw0MTI.jpg",
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
            }
        },
        mounted () {
            this.router = useRoute();
            const { id }: { id: number }  = useRoute().params;
        }
    }
</script>

<style lang="scss" scoped>

</style>