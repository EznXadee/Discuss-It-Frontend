<template>
    <v-app>
        <!-- Header -->
        <v-container class="text-center py-4">
            <img src="@/assets/logo.svg" alt="discuss it logo" style="height: 50px;" />
        </v-container>
        <hr />

        <main class="main-container">
            <div class="login-card">
                <h2 class="login-title">Expert Login</h2>
                <form>
                    <div class="form-group">
                        <label for="email" class="form-label">Email / Cell#</label>
                        <input
                            id="email"
                            type="text"
                            placeholder="Enter email or cell#"
                            class="form-input"
                        />
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
                    <button type="submit" class="submit-button">Continue</button>
                    <div class="text-center mt-4">
                        <a href="#" class="forgot-password">Forgot Password</a>
                    </div>
                </form>
                <div class="text-center mt-6">
                    <span class="not-registered">Not Registered? </span>
                    <a href="#" class="join-us">Join us</a>
                </div>
            </div>
        </main>

        <!-- Footer -->
        <v-footer class="footer">
            <div>
                <img src="@/assets/logo.svg" alt="discuss it logo" style="height: 50px;" />
            </div>
            <div class="text-caption">
                Copyright © 2024 discussit
            </div>
        </v-footer>
    </v-app>
</template>

<script>
export default {
    name: "ExpertLogin",
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
    height: calc(100svh - 200px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.login-card {
    background-color: #ffffff;
    border-radius: 8px;
    padding: 32px;
    width: 100%;
    max-width: 400px;
    flex-shrink: 0;
}

.login-title {
    font-size: 1.5rem;
    font-weight: 600;
    text-align: center;
    margin-bottom: 24px;
}

.form-group {
    margin-bottom: 16px;
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
}

.submit-button:hover {
    background-color: #2b6cb0;
}

.forgot-password {
    font-size: 0.875rem;
    color: #4e5052;
    text-decoration: none;
    transition: color 0.2s;
}

.forgot-password:hover {
    text-decoration: underline;
    color: #2b6cb0;
}

.not-registered {
    font-size: 0.875rem;
    color: #718096;
}

.join-us {
    font-size: 0.875rem;
    font-weight: 600;
    color: #7e858b;
    text-decoration: none;
    transition: color 0.2s;
}

.join-us:hover {
    text-decoration: underline;
    color: #2b6cb0;
}

.footer {
    background-color: #424242;
    color: #ffffff;
    text-align: center;
    padding: 16px;
    flex-shrink: 0;
    display: flex;
    justify-content: space-between;
}
</style>
