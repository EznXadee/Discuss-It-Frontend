<template>
    <v-app>
        <!-- Header -->
        <v-container class="text-center py-4">
            <img src="@/assets/logo.svg" alt="discuss it logo" style="height: 50px;" />
        </v-container>
        <hr />

        <main class="main-container">
            <div class="verification-card">
                <h2 class="verification-title">Verification</h2>
                <div class="verification-section">
                    <div class="verification-method">
                        <h1 class="icon">@</h1>
                        <p>Please check your email</p>
                        <p>We've sent a code to <strong>john.doe@gmail.com</strong></p>
                        <div class="otp-inputs">
                            <v-otp-input
                                v-model="otp"
                                :length="4"
                                variant="solo"
                                :rules="[isOtpValid]"
                            ></v-otp-input>
                        </div>
                        <button type="submit" class="verify-button" @click.prevent="verifyOtp">Verify</button>
                        <div class="resend-section">
                            Didn't get the code? <a href="#" class="resend-link" @click.prevent="resendOtp">Resend OTP</a>
                        </div>
                    </div>
                    <div class="divider"></div>
                    <div class="verification-method">
                        <h1 class="icon">📱</h1>
                        <p>Please check your phone messages</p>
                        <p>We've sent a code to 99898*****</p>
                        <div class="otp-inputs">
                            <v-otp-input
                                v-model="otp"
                                :length="4"
                                variant="solo"
                                :rules="[isOtpValid]"
                            ></v-otp-input>
                        </div>
                        <button type="submit" class="verify-button" disabled>Verify</button>
                        <div class="resend-section">
                            Didn't get the code? <a href="#" class="resend-link" @click.prevent="resendOtp">Resend OTP</a>
                        </div>
                    </div>
                </div>
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

<script>
export default {
    name: "PhoneVerification",
    data() {
        return {
            otp: "", // Use a string to store the OTP entered by the user
            correctOtp: "1234", // Example correct OTP for validation
            showError: false,
        };
    },
    methods: {
        verifyOtp() {
            if (this.otp === this.correctOtp) {
                this.showError = false;
                alert("OTP Verified Successfully!");
            } else {
                this.showError = true;
            }
        },
        resendOtp() {
            alert("OTP Resent Successfully!");
        },
        isOtpValid(value) {
            return /^[0-9]{4}$/.test(value) || "OTP must be 4 digits.";
        },
    },
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
    height: calc(100vh - 150px);
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
    max-width: 600px;
    text-align: center;
}

.verification-title {
    font-size: 1.8rem;
    font-weight: 600;
    margin-bottom: 24px;
}

.verification-section {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 24px;
    margin-top: 24px;
}

.verification-method {
    flex: 1;
    text-align: center;
}

.icon {
    font-size: 3rem;
    color: #3182ce;
    margin-bottom: 16px;
}

.otp-inputs {
    display: flex;
    justify-content: center;
    gap: 8px;
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

.verify-button:disabled {
    background-color: #cbd5e0;
    cursor: not-allowed;
}

.verify-button:hover:enabled {
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

.divider {
    width: 2px;
    background-color: #e2e8f0;
    height: auto;
}

.footer {
    background-color: #424242;
    color: #ffffff;
    text-align: center;
    padding: 16px;
    flex-shrink: 0;
}
</style>
