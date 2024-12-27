<template>
    <v-app>
        <!-- Header -->
        <v-container class="text-center py-4">
            <img src="@/assets/logo.svg" alt="discuss it logo" style="height: 50px;" />
        </v-container>
        <hr />

        <main class="main-container">
            <div class="create-account-card">
                <h2 class="create-account-title">Create Account</h2>
                <form>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="first-name" class="form-label">First Name</label>
                            <input
                                id="first-name"
                                type="text"
                                placeholder="First Name"
                                class="form-input"
                            />
                        </div>
                        <div class="form-group">
                            <label for="last-name" class="form-label">Last Name</label>
                            <input
                                id="last-name"
                                type="text"
                                placeholder="Last Name"
                                class="form-input"
                            />
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="mobile" class="form-label">Mobile#</label>
                            <input
                                id="mobile"
                                type="text"
                                placeholder="+1"
                                class="form-input"
                            />
                        </div>
                        <div class="form-group">
                            <label for="email" class="form-label">Email</label>
                            <input
                                id="email"
                                type="email"
                                placeholder="Enter email address"
                                class="form-input"
                            />
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="country" class="form-label">Country</label>
                            <select id="country" class="form-input">
                                <option value="">Select Country</option>
                                <option value="US">United States</option>
                                <option value="CA">Canada</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="state" class="form-label">State</label>
                            <select id="state" class="form-input">
                                <option value="">Select State</option>
                                <option value="NY">New York</option>
                                <option value="CA">California</option>
                            </select>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="timezone" class="form-label">Time Zone</label>
                            <select id="timezone" class="form-input">
                                <option value="">Select Time Zone</option>
                                <option value="EST">EST</option>
                                <option value="PST">PST</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="password" class="form-label">Password</label>
                            <input
                                id="password"
                                type="password"
                                placeholder="Enter password"
                                class="form-input"
                            />
                        </div>
                    </div>
                    <div class="form-group payment-group">
                        <label class="form-label">Method of Payment</label>
                        <div>
                            <label>
                                <input type="radio" name="payment" value="paypal" checked /> PayPal
                            </label>
                            <label>
                                <input type="radio" name="payment" value="credit-card" /> Credit Card
                            </label>
                        </div>
                    </div>

                    <!-- Profile Picture Section -->
                    <div class="form-group">
                        <label for="profile-picture" class="form-label">Profile Picture</label>
                        <div class="upload-container">
                            <input
                                type="file"
                                id="profile-picture"
                                accept="image/png, image/jpeg"
                                class="file-input"
                            />
                            <p class="upload-hint">Accepted file types: JPG, PNG<br>For best results, upload a square image at least 200px by 200px</p>
                        </div>
                    </div>

                    <v-button type="button" class="submit-button" @click="handleClick">Continue</v-button>
                </form>
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
import router from '@/router';

export default {
    name: "CreateAccount",

    methods: {
        handleClick(e) {
            e.preventDefault();
            router.push('/verification');
            
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
    height: calc(100svh - 150px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.create-account-card {
    background-color: #ffffff;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    padding: 32px;
    width: 100%;
    max-width: 600px;
    flex-shrink: 0;
}

.create-account-title {
    font-size: 1.5rem;
    font-weight: 600;
    text-align: center;
    margin-bottom: 24px;
}

.form-row {
    display: flex;
    justify-content: space-between;
    gap: 16px;
    margin-bottom: 16px;
}

.form-group {
    flex: 1;
}

.form-label {
    display: block;
    font-size: 0.875rem;
    font-weight: 500;
    color: #4a5568;
    margin-bottom: 4px;
}

.form-input {
    width: 100%;
    padding: 8px 16px;
    border: 1px solid #cbd5e0;
    border-radius: 4px;
    font-size: 1rem;
    outline: none;
    transition: border-color 0.2s, box-shadow 0.2s;
}

.form-input:focus {
    border-color: #3182ce;
    box-shadow: 0 0 0 3px rgba(66, 153, 225, 0.5);
}

.payment-group {
    margin-bottom: 24px;
}

.upload-container {
    border: 2px dashed #cbd5e0;
    border-radius: 4px;
    padding: 16px;
    text-align: center;
    margin-top: 8px;
}

.file-input {
    display: block;
    width: 100%;
    margin: 0 auto;
}

.upload-hint {
    font-size: 0.875rem;
    color: #718096;
    margin-top: 8px;
}

.submit-button {
    width: 100%;
    padding: 12px;
    background-color: #3182ce;
    color: #ffffff;
    font-weight: 600;
    border-radius: 4px;
    border: none;
    cursor: pointer;
    transition: background-color 0.2s;
    display: flex;
    justify-content: center;
    align-items: center;
}

.submit-button:hover {
    background-color: #2b6cb0;
}

.footer {
    background-color: #424242;
    color: #ffffff;
    text-align: center;
    padding: 16px;
    flex-shrink: 0;
}
</style>
