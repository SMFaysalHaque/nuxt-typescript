<template>
    <div class="my-10">
        <!-- submit area -->
        <div class="p-5 bg-slate-200 mb-5">
            <div class="text-center mb-2">
                <p class="font-bold text-xl">Contact Us</p>
            </div>
            <div>
                <div class="grid grid-cols-2 mb-2">
                    <div>
                        <p>Name:</p>
                        <input type="text" name="name" id="name" v-model="info.name">
                    </div>
                    <div>
                        <p>Mobile:</p>
                        <input type="tel" name="mobile" id="mobile" v-model="info.mobile">
                    </div>
                </div>
                <div class="grid grid-cols-2 mb-2">
                    <div>
                        <p>Address:</p>
                        <input type="text" name="address" id="address" v-model="info.address">
                    </div>
                    <div>
                        <p>Gender</p>
                        <input type="radio" id="male" value="Male" v-model="info.picked" />
                        <label for="male">Male</label>

                        <input type="radio" id="female" value="Female" v-model="info.picked" />
                        <label for="female">Female</label>
                    </div>
                </div>
                <div class="grid grid-cols-1 mb-2">
                    <div>
                        <p>Message:</p>
                        <textarea name="message" id="message" rows="5" class="w-full" v-model="info.message"></textarea>
                    </div>
                </div>
            </div>
            <div>
                <button @click="addMessage" type="submit" class="border border-blue-500 hover:text-white hover:bg-blue-500 transform duration-200 px-8 py-1">Submit</button>
            </div>
        </div>
        <!-- massage area -->
        <div class="p-5">
            <div class="text-center mb-2">
                <p class="font-bold text-xl">Message</p>
            </div>
            <div v-for="(info, index) in infos" :key="index" class="border p-3 mb-2">
                <div class="grid grid-cols-3 mb-2">
                    <p>Name: {{ info.name }} </p>
                    <p>Gender: {{ info.picked }}</p>
                    <button @click="remove(index)" class="border border-red-600 w-fit mx-auto px-5 hover:bg-red-600 hover:text-white transform duration-200">Remove</button>
                </div>
                <div class="grid grid-cols-2 mb-2">
                    <p>Mobile: {{ info.mobile }}</p>
                    <p>Address: {{ info.address }}</p>
                </div>
                <div class="grid grid-cols-1">
                    <p class="mb-2">Message: </p>
                    <p class="break-words">{{ info.message }}</p>
                    <!-- <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti dolore sequi adipisci illo odit inventore quasi sapiente ullam eius doloribus deserunt minima nam sint, et officia fugit molestiae autem sunt tenetur natus ratione nulla officiis? Impedit error maxime perspiciatis voluptatum.</p> -->
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { info } from '../types/contact'
    export default {
        data() {
            return {
                picked: 'Male' as string,
                getItem: '' as any,
                info: {
                    name: '',
                    mobile: '',
                    address: '',
                    message: '',
                    picked: ''
                } as info,
                infos: [] as info[]
            }
        },
        mounted(){
            this.getItem = (localStorage.getItem('addMessage'))
            this.infos = JSON.parse(this.getItem) ? JSON.parse(this.getItem) : []
        },
        methods: {
            addMessage () {
                if (this.info.name !== ''){
                    this.infos.push(this.info)
                    localStorage.setItem('addMessage', JSON.stringify(this.infos))
                } else {
                    alert ('Fill up all input field')
                }
                this.info = { 
                    name: '',
                    mobile: '',
                    address: '',
                    message: '',
                    picked: ''
                };
                // this.info.name = '',
                // this.info.mobile = '',
                // this.info.address = '',
                // this.info.message = '',
                // this.info.picked = ''
            },
            remove (i:number) {
                this.infos.splice(i, 1)
                localStorage.setItem('addMessage', JSON.stringify(this.infos));
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>