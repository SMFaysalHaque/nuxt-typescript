<template>
    <div class="my-10">
        <!-- submit area -->
        <div class="p-5 bg-slate-200 mb-5">
            <div class="text-center mb-2">
                <p class="font-bold text-xl">Contact Us</p>
            </div>
            <div>
                <div class="grid grid-cols-3  mb-2">
                    <div>
                        <p>Name:</p>
                        <input type="text" name="name" id="name" v-model="info.name">
                        <div v-if="nameShow" @click="close" class="flex justify-between items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900"> {{ err.errorName }} </p>
                            <svg class="fill-red-900" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none">
                                <path d="M19.492 3.48514C19.2278 3.49138 18.9767 3.60198 18.7938 3.79276L12.0008 10.5857L5.20785 3.79276C5.11454 3.69685 5.00294 3.62063 4.87965 3.56863C4.75636 3.51663 4.62389 3.4899 4.49008 3.49003C4.29123 3.49027 4.09696 3.54979 3.9321 3.66098C3.76724 3.77217 3.63927 3.92998 3.56454 4.11425C3.4898 4.29852 3.47169 4.50089 3.51253 4.6955C3.55336 4.89011 3.65129 5.06813 3.79379 5.20682L10.5868 11.9998L3.79379 18.7928C3.69781 18.8849 3.62119 18.9953 3.5684 19.1174C3.51562 19.2395 3.48773 19.371 3.48638 19.504C3.48503 19.637 3.51023 19.769 3.56052 19.8922C3.61081 20.0154 3.68517 20.1273 3.77925 20.2214C3.87333 20.3154 3.98523 20.3898 4.10841 20.4401C4.23159 20.4904 4.36356 20.5156 4.4966 20.5142C4.62964 20.5129 4.76108 20.485 4.88321 20.4322C5.00534 20.3794 5.1157 20.3028 5.20785 20.2068L12.0008 13.4139L18.7938 20.2068C18.8859 20.3028 18.9963 20.3794 19.1184 20.4322C19.2406 20.485 19.372 20.5129 19.505 20.5142C19.6381 20.5156 19.77 20.4904 19.8932 20.4401C20.0164 20.3898 20.1283 20.3154 20.2224 20.2214C20.3165 20.1273 20.3908 20.0154 20.4411 19.8922C20.4914 19.769 20.5166 19.637 20.5153 19.504C20.5139 19.371 20.486 19.2395 20.4332 19.1174C20.3804 18.9953 20.3038 18.8849 20.2078 18.7928L13.4149 11.9998L20.2078 5.20682C20.3534 5.06729 20.4533 4.88704 20.4946 4.6897C20.5359 4.49237 20.5165 4.28717 20.4391 4.10102C20.3617 3.91486 20.2299 3.75644 20.0609 3.64654C19.8919 3.53664 19.6936 3.48038 19.492 3.48514Z" />                                                 
                            </svg>
                        </div>
                    </div>
                    <div>
                        <p>Mobile:</p>
                        <input type="tel" name="mobile" id="mobile" v-model="info.mobile">
                        <div v-if="mobileShow" @click="close" class="flex justify-between items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorMobile }}</p>
                            <svg class="fill-red-900" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none">
                                <path d="M19.492 3.48514C19.2278 3.49138 18.9767 3.60198 18.7938 3.79276L12.0008 10.5857L5.20785 3.79276C5.11454 3.69685 5.00294 3.62063 4.87965 3.56863C4.75636 3.51663 4.62389 3.4899 4.49008 3.49003C4.29123 3.49027 4.09696 3.54979 3.9321 3.66098C3.76724 3.77217 3.63927 3.92998 3.56454 4.11425C3.4898 4.29852 3.47169 4.50089 3.51253 4.6955C3.55336 4.89011 3.65129 5.06813 3.79379 5.20682L10.5868 11.9998L3.79379 18.7928C3.69781 18.8849 3.62119 18.9953 3.5684 19.1174C3.51562 19.2395 3.48773 19.371 3.48638 19.504C3.48503 19.637 3.51023 19.769 3.56052 19.8922C3.61081 20.0154 3.68517 20.1273 3.77925 20.2214C3.87333 20.3154 3.98523 20.3898 4.10841 20.4401C4.23159 20.4904 4.36356 20.5156 4.4966 20.5142C4.62964 20.5129 4.76108 20.485 4.88321 20.4322C5.00534 20.3794 5.1157 20.3028 5.20785 20.2068L12.0008 13.4139L18.7938 20.2068C18.8859 20.3028 18.9963 20.3794 19.1184 20.4322C19.2406 20.485 19.372 20.5129 19.505 20.5142C19.6381 20.5156 19.77 20.4904 19.8932 20.4401C20.0164 20.3898 20.1283 20.3154 20.2224 20.2214C20.3165 20.1273 20.3908 20.0154 20.4411 19.8922C20.4914 19.769 20.5166 19.637 20.5153 19.504C20.5139 19.371 20.486 19.2395 20.4332 19.1174C20.3804 18.9953 20.3038 18.8849 20.2078 18.7928L13.4149 11.9998L20.2078 5.20682C20.3534 5.06729 20.4533 4.88704 20.4946 4.6897C20.5359 4.49237 20.5165 4.28717 20.4391 4.10102C20.3617 3.91486 20.2299 3.75644 20.0609 3.64654C19.8919 3.53664 19.6936 3.48038 19.492 3.48514Z" />                                                 
                            </svg>
                        </div>
                    </div>
                    <div>
                        <p>E-mail:</p>
                        <input type="email" name="email" id="email" v-model="info.email">
                        <div v-if="emailShow" @click="close" class="flex justify-between items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorEmail }}</p>
                            <svg class="fill-red-900" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none">
                                <path d="M19.492 3.48514C19.2278 3.49138 18.9767 3.60198 18.7938 3.79276L12.0008 10.5857L5.20785 3.79276C5.11454 3.69685 5.00294 3.62063 4.87965 3.56863C4.75636 3.51663 4.62389 3.4899 4.49008 3.49003C4.29123 3.49027 4.09696 3.54979 3.9321 3.66098C3.76724 3.77217 3.63927 3.92998 3.56454 4.11425C3.4898 4.29852 3.47169 4.50089 3.51253 4.6955C3.55336 4.89011 3.65129 5.06813 3.79379 5.20682L10.5868 11.9998L3.79379 18.7928C3.69781 18.8849 3.62119 18.9953 3.5684 19.1174C3.51562 19.2395 3.48773 19.371 3.48638 19.504C3.48503 19.637 3.51023 19.769 3.56052 19.8922C3.61081 20.0154 3.68517 20.1273 3.77925 20.2214C3.87333 20.3154 3.98523 20.3898 4.10841 20.4401C4.23159 20.4904 4.36356 20.5156 4.4966 20.5142C4.62964 20.5129 4.76108 20.485 4.88321 20.4322C5.00534 20.3794 5.1157 20.3028 5.20785 20.2068L12.0008 13.4139L18.7938 20.2068C18.8859 20.3028 18.9963 20.3794 19.1184 20.4322C19.2406 20.485 19.372 20.5129 19.505 20.5142C19.6381 20.5156 19.77 20.4904 19.8932 20.4401C20.0164 20.3898 20.1283 20.3154 20.2224 20.2214C20.3165 20.1273 20.3908 20.0154 20.4411 19.8922C20.4914 19.769 20.5166 19.637 20.5153 19.504C20.5139 19.371 20.486 19.2395 20.4332 19.1174C20.3804 18.9953 20.3038 18.8849 20.2078 18.7928L13.4149 11.9998L20.2078 5.20682C20.3534 5.06729 20.4533 4.88704 20.4946 4.6897C20.5359 4.49237 20.5165 4.28717 20.4391 4.10102C20.3617 3.91486 20.2299 3.75644 20.0609 3.64654C19.8919 3.53664 19.6936 3.48038 19.492 3.48514Z" />                                                 
                            </svg>
                        </div>
                    </div>
                </div>
                <div class="grid grid-cols-2 mb-2">
                    <div>
                        <p>Address:</p>
                        <input type="text" name="address" id="address" v-model="info.address">
                        <div v-if="addressShow" @click="close" class="flex justify-between items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorAddress }}</p>
                            <svg class="fill-red-900" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none">
                                <path d="M19.492 3.48514C19.2278 3.49138 18.9767 3.60198 18.7938 3.79276L12.0008 10.5857L5.20785 3.79276C5.11454 3.69685 5.00294 3.62063 4.87965 3.56863C4.75636 3.51663 4.62389 3.4899 4.49008 3.49003C4.29123 3.49027 4.09696 3.54979 3.9321 3.66098C3.76724 3.77217 3.63927 3.92998 3.56454 4.11425C3.4898 4.29852 3.47169 4.50089 3.51253 4.6955C3.55336 4.89011 3.65129 5.06813 3.79379 5.20682L10.5868 11.9998L3.79379 18.7928C3.69781 18.8849 3.62119 18.9953 3.5684 19.1174C3.51562 19.2395 3.48773 19.371 3.48638 19.504C3.48503 19.637 3.51023 19.769 3.56052 19.8922C3.61081 20.0154 3.68517 20.1273 3.77925 20.2214C3.87333 20.3154 3.98523 20.3898 4.10841 20.4401C4.23159 20.4904 4.36356 20.5156 4.4966 20.5142C4.62964 20.5129 4.76108 20.485 4.88321 20.4322C5.00534 20.3794 5.1157 20.3028 5.20785 20.2068L12.0008 13.4139L18.7938 20.2068C18.8859 20.3028 18.9963 20.3794 19.1184 20.4322C19.2406 20.485 19.372 20.5129 19.505 20.5142C19.6381 20.5156 19.77 20.4904 19.8932 20.4401C20.0164 20.3898 20.1283 20.3154 20.2224 20.2214C20.3165 20.1273 20.3908 20.0154 20.4411 19.8922C20.4914 19.769 20.5166 19.637 20.5153 19.504C20.5139 19.371 20.486 19.2395 20.4332 19.1174C20.3804 18.9953 20.3038 18.8849 20.2078 18.7928L13.4149 11.9998L20.2078 5.20682C20.3534 5.06729 20.4533 4.88704 20.4946 4.6897C20.5359 4.49237 20.5165 4.28717 20.4391 4.10102C20.3617 3.91486 20.2299 3.75644 20.0609 3.64654C19.8919 3.53664 19.6936 3.48038 19.492 3.48514Z" />                                                 
                            </svg>
                        </div>
                    </div>
                    <div>
                        <p>Gender</p>
                        <input type="radio" id="male" value="Male" v-model="info.picked" />
                        <label for="male">Male</label>

                        <input type="radio" id="female" value="Female" v-model="info.picked" />
                        <label for="female">Female</label>

                        <div v-if="genderShow" @click="close" class="flex justify-between items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorPicked }}</p>
                            <svg class="fill-red-900" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none">
                                <path d="M19.492 3.48514C19.2278 3.49138 18.9767 3.60198 18.7938 3.79276L12.0008 10.5857L5.20785 3.79276C5.11454 3.69685 5.00294 3.62063 4.87965 3.56863C4.75636 3.51663 4.62389 3.4899 4.49008 3.49003C4.29123 3.49027 4.09696 3.54979 3.9321 3.66098C3.76724 3.77217 3.63927 3.92998 3.56454 4.11425C3.4898 4.29852 3.47169 4.50089 3.51253 4.6955C3.55336 4.89011 3.65129 5.06813 3.79379 5.20682L10.5868 11.9998L3.79379 18.7928C3.69781 18.8849 3.62119 18.9953 3.5684 19.1174C3.51562 19.2395 3.48773 19.371 3.48638 19.504C3.48503 19.637 3.51023 19.769 3.56052 19.8922C3.61081 20.0154 3.68517 20.1273 3.77925 20.2214C3.87333 20.3154 3.98523 20.3898 4.10841 20.4401C4.23159 20.4904 4.36356 20.5156 4.4966 20.5142C4.62964 20.5129 4.76108 20.485 4.88321 20.4322C5.00534 20.3794 5.1157 20.3028 5.20785 20.2068L12.0008 13.4139L18.7938 20.2068C18.8859 20.3028 18.9963 20.3794 19.1184 20.4322C19.2406 20.485 19.372 20.5129 19.505 20.5142C19.6381 20.5156 19.77 20.4904 19.8932 20.4401C20.0164 20.3898 20.1283 20.3154 20.2224 20.2214C20.3165 20.1273 20.3908 20.0154 20.4411 19.8922C20.4914 19.769 20.5166 19.637 20.5153 19.504C20.5139 19.371 20.486 19.2395 20.4332 19.1174C20.3804 18.9953 20.3038 18.8849 20.2078 18.7928L13.4149 11.9998L20.2078 5.20682C20.3534 5.06729 20.4533 4.88704 20.4946 4.6897C20.5359 4.49237 20.5165 4.28717 20.4391 4.10102C20.3617 3.91486 20.2299 3.75644 20.0609 3.64654C19.8919 3.53664 19.6936 3.48038 19.492 3.48514Z" />                                                 
                            </svg>
                        </div>
                    </div>
                </div>
                <div class="grid grid-cols-1 mb-2">
                    <div>
                        <p>Message:</p>
                        <textarea name="message" id="message" rows="5" class="w-full" v-model="info.message"></textarea>
                        <div v-if="messageShow" @click="close" class="flex justify-between items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorMessage }}</p>
                            <svg class="fill-red-900" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none">
                                <path d="M19.492 3.48514C19.2278 3.49138 18.9767 3.60198 18.7938 3.79276L12.0008 10.5857L5.20785 3.79276C5.11454 3.69685 5.00294 3.62063 4.87965 3.56863C4.75636 3.51663 4.62389 3.4899 4.49008 3.49003C4.29123 3.49027 4.09696 3.54979 3.9321 3.66098C3.76724 3.77217 3.63927 3.92998 3.56454 4.11425C3.4898 4.29852 3.47169 4.50089 3.51253 4.6955C3.55336 4.89011 3.65129 5.06813 3.79379 5.20682L10.5868 11.9998L3.79379 18.7928C3.69781 18.8849 3.62119 18.9953 3.5684 19.1174C3.51562 19.2395 3.48773 19.371 3.48638 19.504C3.48503 19.637 3.51023 19.769 3.56052 19.8922C3.61081 20.0154 3.68517 20.1273 3.77925 20.2214C3.87333 20.3154 3.98523 20.3898 4.10841 20.4401C4.23159 20.4904 4.36356 20.5156 4.4966 20.5142C4.62964 20.5129 4.76108 20.485 4.88321 20.4322C5.00534 20.3794 5.1157 20.3028 5.20785 20.2068L12.0008 13.4139L18.7938 20.2068C18.8859 20.3028 18.9963 20.3794 19.1184 20.4322C19.2406 20.485 19.372 20.5129 19.505 20.5142C19.6381 20.5156 19.77 20.4904 19.8932 20.4401C20.0164 20.3898 20.1283 20.3154 20.2224 20.2214C20.3165 20.1273 20.3908 20.0154 20.4411 19.8922C20.4914 19.769 20.5166 19.637 20.5153 19.504C20.5139 19.371 20.486 19.2395 20.4332 19.1174C20.3804 18.9953 20.3038 18.8849 20.2078 18.7928L13.4149 11.9998L20.2078 5.20682C20.3534 5.06729 20.4533 4.88704 20.4946 4.6897C20.5359 4.49237 20.5165 4.28717 20.4391 4.10102C20.3617 3.91486 20.2299 3.75644 20.0609 3.64654C19.8919 3.53664 19.6936 3.48038 19.492 3.48514Z" />                                                 
                            </svg>
                        </div>
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
import { err, info } from '../types/contact'
    export default {
        data() {
            return {
                picked: 'Male' as string,
                getItem: '' as any,
                show: false as boolean,
                nameShow: false as boolean,
                mobileShow: false as boolean,
                emailShow: false as boolean,
                addressShow: false as boolean,
                genderShow: false as boolean,
                messageShow: false as boolean,

                info: {
                    name: '',
                    mobile: '',
                    email: '',
                    address: '',
                    message: '',
                    picked: ''
                } as info,
                err: {
                    errorName: 'Fill up name field!',
                    errorMobile: 'Fill up valid mobile number!',
                    errorEmail: 'Fill up valid email!',
                    errorAddress: 'Fill up address field!',
                    errorMessage: 'Fill up message field!',
                    errorPicked: 'Fill up gender field!'
                } as err,
                infos: [] as info[]
            }
        },
        mounted(){
            this.getItem = (localStorage.getItem('addMessage'))
            this.infos = JSON.parse(this.getItem) ? JSON.parse(this.getItem) : []
            console.log('aaa', this.isValidMobile(this.info.mobile));
        },
        methods: {
            resetForm () {
                this.info = { 
                    name: '',
                    mobile: '',
                    email: '',
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
            clearErr () {
                this.nameShow = false
                this.mobileShow = false
                this.emailShow = false
                this.addressShow = false
                this.genderShow = false
                this.messageShow = false
            },
            addErr () {
                this.nameShow = true
                this.mobileShow = true
                this.emailShow = true
                this.addressShow = true
                this.genderShow = true
                this.messageShow = true
            },
            addMessage () {
                if (this.info.name !== '' && this.info.mobile !== '' && this.info.email !== '' && this.info.address !== '' && this.info.message !== '' && this.info.picked !== '') {
                    if (this.info.mobile !== '' && this.info.email !== '') {
                        if (this.isValidMobile(this.info.mobile) === true && this.isValidEmail() === true) {
                            this.infos.push(this.info)
                            localStorage.setItem('addMessage', JSON.stringify(this.infos))
                            this.clearErr()
                        } else if (this.isValidMobile(this.info.mobile) === false || this.isValidEmail() === false) {
                            // console.log("alert");
                            // this.isValidMobile(this.info.mobile) === false ? console.log('mobile alert', !this.show) : console.log('email alert', this.show)
                            // this.isValidMobile(this.info.mobile) === false ? !this.show : this.show
                            if (this.isValidMobile(this.info.mobile) === false) {
                                this.mobileShow = true
                                console.log('mobile alert')
                            } else if (this.isValidEmail() === false) {
                                this.emailShow = true
                                console.log('email alert')
                            }
                        }
                    }
                } else if (this.info.name === '') {
                    this.nameShow = true as boolean
                } else if (this.info.address === '') {
                    this.addressShow = true as boolean
                } else if (this.info.picked === '') {
                    this.genderShow = true as boolean
                } else if (this.info.message === '') {
                    this.messageShow = true as boolean
                } else {
                    this.addErr ()
                }
                this.resetForm ()
                // this.isValidMobile ()
            },
            remove (i:number) {
                this.infos.splice(i, 1)
                localStorage.setItem('addMessage', JSON.stringify(this.infos));
            },
            close () {
                this.show = false
            },
            isValidMobile(mobile: any) {
            const validMobile: any = (this.info.mobile)
                .toLowerCase()
                .match(/^(?:\+88|88)?(01[3-9]\d{8})$/);
            if (!validMobile) {
                // alert("Please add a valid phone!!!");
                return false;
            }
            return true;
            },
            isValidEmail() {
            const validEmail = String(this.info.email)
                .toLowerCase()
                .match(
                /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
                );
            if (!validEmail) {
                // alert("Please add a valid email!!!");
                return false;
            }
            return true;
            },
        },
    }
</script>

<style lang="scss" scoped>

</style>