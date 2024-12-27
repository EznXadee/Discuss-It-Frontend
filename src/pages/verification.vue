<template>
    <v-app>
        <!-- Header -->
        <v-container class="text-center py-4">
            <img src="@/assets/logo.svg" alt="discuss it logo" style="height: 50px;" />
        </v-container>
        <hr />

        <main class="main-container">
            <div v-if="currentPage === 1" class="verification-card">
                <h2 class="verification-title">Email Verification</h2>
                <h1 class="topic">@</h1>
                <div class="verification-instructions">
                    <p>Please check your email</p>
                    <p>We've sent a code to <strong>john.doe@gmail.com</strong></p>
                </div>
                <form @submit.prevent="verifyOtp">
                    <div class="otp-inputs">
                        <v-otp-input 
                            v-model="otp"
                            :length="4"
                            variant="solo"
                            :rules="[isOtpValid]"
                        ></v-otp-input>
                    </div>
                    <div v-if="showError" class="error-message">Enter valid OTP</div>
                    <button type="submit" class="verify-button">Verify</button>
                </form>
                <div class="resend-section">
                    Didn't get the code? <a href="#" class="resend-link" @click.prevent="resendOtp">Resend OTP</a>
                </div>
            </div>

            <div v-else-if="currentPage === 2">
                <PhoneVerification />
            </div>
        </main>

        <!-- Footer -->
        <v-footer class="footer">
            <div class="text-caption">
                Copyright © 2024 discuss<span class="text-orange">it</span>
            </div>
        </v-footer>
    </v-app>
</template>

<script setup>
import { ref } from "vue";
import { useRouter, useRoute } from "vue-router"; // Import router utilities
import PhoneVerification from '@/components/Login/Verifcation2.vue';

const otp = ref(""); // Reactive variable for OTP
const correctOtp = "1234"; // Example correct OTP for validation
const showError = ref(false); // Reactive variable for error message visibility
const router = useRouter();
const route = useRoute();

const currentPage = ref(Number(route.query.page) || 1); // Default page is 1

const verifyOtp = () => {
    if (otp.value === correctOtp) {
        showError.value = false;
        // Update query parameter to page=2
        router.push({ query: { ...route.query, page: 2 } });
        currentPage.value = 2; // Update the local state
    } else {
        showError.value = true;
    }
};

const resendOtp = () => {
    alert("OTP Resent Successfully!");
};

const isOtpValid = (value) => {
    return /^[0-9]{4}$/.test(value) || "OTP must be 4 digits.";
};
</script>

<style scoped>
.text-orange {
    color: #ff9800;
}

.py-4 {
    padding-top: 16px;
    padding-bottom: 16px;
}

.text-center {
    text-align: center;
}

.main-container {
    height: calc(100svh - 150px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.verification-card {
    background-color: #ffffff;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    padding: 32px;
    width: 100%;
    max-width: 400px;
    text-align: center;
}

.verification-title {
    font-size: 1.5rem;
    font-weight: 600;
    margin-bottom: 16px;
}

.verification-instructions {
    font-size: 0.875rem;
    color: #4a5568;
    margin-bottom: 24px;
}

.otp-inputs {
    display: flex;
    justify-content: center;
    gap: 8px;
    margin-bottom: 16px;
}

.otp-input {
    width: 40px;
    height: 40px;
    text-align: center;
    font-size: 1.25rem;
    border: 1px solid #cbd5e0;
    border-radius: 4px;
    outline: none;
    transition: border-color 0.2s, box-shadow 0.2s;
}

.otp-input:focus {
    border-color: #3182ce;
    box-shadow: 0 0 0 3px rgba(66, 153, 225, 0.5);
}

.error-message {
    font-size: 0.875rem;
    color: #e53e3e;
    margin-bottom: 16px;
}

.verify-button {
    width: 100%;
    padding: 12px;
    background-color: #3182ce;
    color: #ffffff;
    font-weight: 600;
    border-radius: 4px;
    border: none;
    cursor: pointer;
    transition: background-color 0.2s;
}

.verify-button:hover {
    background-color: #2b6cb0;
}

.resend-section {
    font-size: 0.875rem;
    color: #4a5568;
    margin-top: 16px;
}

.resend-link {
    color: #3182ce;
    font-weight: 600;
    text-decoration: none;
    cursor: pointer;
}

.resend-link:hover {
    text-decoration: underline;
}

.footer {
    background-color: #424242;
    color: #ffffff;
    text-align: center;
    padding: 16px;
    flex-shrink: 0;
}

.topic {
    font-size: 80px;
}
</style>
