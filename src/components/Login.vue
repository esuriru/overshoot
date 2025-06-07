<template>
    <div class="min-h-screen flex items-center justify-center bg-gray-100 p-4 font-inter">
    <div class="bg-white p-8 rounded-lg shadow-xl w-full max-w-md">
        <h2 class="text-3xl font-bold text-center text-gray-800 mb-8">Login</h2>
        <form @submit.prevent="handleLogin">
            <div class="mb-6">
                <label for="email" class="block text-gray-700 text-sm font-semibold mb-2">Email</label>
                <input 
                    type="text" 
                    id="email" 
                    placeholder="you@example.com" 
                    required
                />
            </div>

            <div class="mb-8">
                <label for="password" class="block text-gray-700 text-sm font-semibold mb-2">Password</label>
                <input 
                    type="password"
                    id="password" 
                    placeholder="********"
                    required
                />
            </div>

            <div v-if="error" class="bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded-lg relative mb-4">{{ error }}</div>

            <div className="flex items-center justify-between">
                <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-4 rounded-lg focus:outline-none focus:shadow-outline-blue focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 transition duration-300 ease-in-out transform hover:scale-105">
                    Login
                </button>
            </div>
        </form>
    </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            username: '',
            password: '',
            error: null,
        };
    },
    methods: {
        handleLogin() {
            // Clear previous error
            this.error = null;

            // Simple validation
            if (!this.username || !this.password) {
                this.error = 'Username and password are required';
                return;
            }

            // Simulate an API request (replace with real API logic)
            const mockApiResponse = {
                success: true, // Set to false to simulate error
                message: 'Login successful',
            };

            // if (mockApiResponse.success) {
            //     this.$router.push('/dashboard'); // Redirect to dashboard
            // } else {
            //     this.error = mockApiResponse.message;
            // }
        },
    },
};
</script>

<style scoped>
</style>
