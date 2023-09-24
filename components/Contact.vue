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
                        <input type="text" name="name" id="name" @input="checkEnableButton" v-model="info.name">
                        <div v-if="nameShow" id="error" class="flex items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900"> {{ err.errorName }} </p>
                        </div>
                    </div>
                    <div>
                        <p>Mobile:</p>
                        <input type="tel" name="mobile" id="mobile" @input="checkEnableButton" v-model="info.mobile">
                        <div v-if="mobileShow" class="flex items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorMobile }}</p>
                        </div>
                    </div>
                    <div>
                        <p>E-mail:</p>
                        <input type="email" name="email" id="email" @input="checkEnableButton" v-model="info.email">
                        <div v-if="emailShow" class="flex items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorEmail }}</p>
                        </div>
                    </div>
                </div>
                <div class="grid grid-cols-2 mb-2">
                    <div>
                        <p>Address:</p>
                        <input type="text" name="address" id="address" @input="checkEnableButton" v-model="info.address">
                        <div v-if="addressShow" class="flex items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorAddress }}</p>
                        </div>
                    </div>
                    <div>
                        <p>Gender</p>
                        <input type="radio" id="male" value="Male" @input="checkEnableButton" v-model="info.picked" />
                        <label for="male">Male</label>

                        <input type="radio" id="female" value="Female" @input="checkEnableButton" v-model="info.picked" />
                        <label for="female">Female</label>

                        <div v-if="genderShow" class="flex items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorPicked }}</p>
                        </div>
                    </div>
                </div>
                <div class="grid grid-cols-1 mb-2">
                    <div>
                        <p>Message:</p>
                        <textarea name="message" id="message" rows="5" class="w-full" @input="checkEnableButton" v-model="info.message"></textarea>
                        <div v-if="messageShow" @click="close" class="flex items-center w-[248px] border border-[#f74e4ee7] bg-[#f74e4ee7] mt-1 px-2 py-[2px]">
                            <p class="text-red-900">{{ err.errorMessage }}</p>
                        </div>
                    </div>
                </div>
            </div>
            <div>
                <button :disabled="!isButtonEnabled" @click="addMessage" type="submit" class="border border-blue-500 hover:text-white hover:bg-blue-500 transform duration-200 px-8 py-1 disabled:bg-gray-400 disabled:cursor-not-allowed">Submit</button>
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
                nameShow: false as boolean,
                mobileShow: false as boolean,
                emailShow: false as boolean,
                addressShow: false as boolean,
                genderShow: false as boolean,
                messageShow: false as boolean,
                timer: '' as any,
                inputValue: '' as any,
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
        computed: {
            isButtonEnabled() {
                this.inputValue = this.info.name.trim() !== '' &&
                    this.info.mobile.trim() !== '' &&
                    this.info.email.trim() !== '' &&
                    this.info.address.trim() !== '' &&
                    this.info.picked.trim() !== '' &&
                    this.info.message.trim() !== ''
                return (
                    this.inputValue
                );
            },
        },
        mounted(){
            this.getItem = (localStorage.getItem('addMessage'))
            this.infos = JSON.parse(this.getItem) ? JSON.parse(this.getItem) : []
        },
        destroyed () {
            document.removeEventListener('click', this.timer)
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
                }
            },
            clearErr () {
                this.nameShow = false
                this.mobileShow = false
                this.emailShow = false
                this.addressShow = false
                this.genderShow = false
                this.messageShow = false
            },
            addMessage () {
                if (this.inputValue) {
                    if (this.info.mobile !== '' && this.info.email !== '') {
                        if (this.isValidMobile(this.info.mobile) === true && this.isValidEmail() === true) {
                            this.infos.push(this.info)
                            localStorage.setItem('addMessage', JSON.stringify(this.infos))
                            this.resetForm()
                        }
                    }
                }
                if (this.info.name === '') {
                    this.nameShow = true
                    this.info.name = ''
                }
                if (this.info.mobile === '' || this.isValidMobile(this.info.mobile) === false) {
                    this.mobileShow = true
                    this.info.mobile = ''
                    this.timer = setTimeout(() => {
                        this.mobileShow = false
                    }, 5000)
                }
                if (this.info.email === '' || this.isValidEmail() === false) {
                    this.emailShow = true
                    this.info.email = ''
                    this.timer = setTimeout(() => {
                        this.emailShow = false
                    }, 5000)
                }
                if (this.info.address === '') {
                    this.addressShow = true
                    this.info.address = ''
                }
                if (this.info.picked === '') {
                    this.genderShow = true
                    this.info.picked = ''
                }
                if (this.info.message === '') {
                    this.messageShow = true
                    this.info.message = ''
                }
                if (this.info.name === '' && this.info.mobile === '' && this.info.email === '' && this.info.address === '' && this.info.picked === '' && this.info.message === '') {
                    this.clearErr ()
                }
            },
            remove (i: number) {
                this.infos.splice(i, 1)
                localStorage.setItem('addMessage', JSON.stringify(this.infos));
            },
            isValidMobile(mobile: any) {
            const validMobile: any = (this.info.mobile)
                .toLowerCase()
                .match(/^(?:\+88|88)?(01[3-9]\d{8})$/);
                if (!validMobile) {
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
                    return false;
                }
                return true;
            },
            checkEnableButton() {
                const areAllFieldsFilled = this.inputValue
                this.isButtonEnabled = areAllFieldsFilled;
            },
        },
    }
</script>

<style scoped>

</style>