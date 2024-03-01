<template>
    <div class="contact-container">
        <h1>Contact Us</h1>
        <p>Have questions or feedback? We'd love to hear from you. Please fill out the form below and we'll get back to you as soon as possible.</p>
        <form>
            <label for="name">Name:</label>
            <input type="text" id="name" name="name">

            <label for="email">Email:</label>
            <input type="email" id="email" name="email">

            <label for="message">Message:</label>
            <textarea id="message" name="message"></textarea>

            <input type="submit" value="Submit">
        </form>
    </div>
</template>

<style scoped>
.contact-container {
    padding: 20px;
}

form {
    display: flex;
    flex-direction: column;
    margin-top: 20px;
}

label {
    margin-top: 10px;
}

input, textarea {
    margin-top: 5px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

input[type="submit"] {
    margin-top: 20px;
    background-color: #4CAF50;
    color: white;
    cursor: pointer;
}

input[type="submit"]:hover {
    background-color: #45a049;
}
</style>