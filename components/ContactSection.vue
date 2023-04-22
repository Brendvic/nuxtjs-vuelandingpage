<template>
	<div id="contact">
	<section class="contact-section">
		<div class="contact-container">
			<h2>Contact Us</h2>
			<form id="contact-form">
				<label for="name">Name</label>
				<input type="text" id="name" name="name" required>

				<label for="email">Email</label>
				<input type="email" id="email" name="email" required>

				<label for="message">Message</label>
				<textarea id="message" name="message" required></textarea>

				<button type="submit">Submit</button>
			</form>
		</div>
	</section>
</div>
</template>

<script>
export default {
	name: 'ContactSection',
	mounted() {
		const form = document.getElementById('contact-form');
		const nameInput = document.getElementById('name');
		const emailInput = document.getElementById('email');
		const messageInput = document.getElementById('message');

		form.addEventListener('submit', (e) => {
			e.preventDefault();
			const name = nameInput.value.trim();
			const email = emailInput.value.trim();
			const message = messageInput.value.trim();

			if (name === '' || email === '' || message === '') {
				alert('Please fill in all fields.');
				return;
			}

			// Replace the URL with the actual endpoint for your form submission
			const endpoint = 'https://example.com/submit';
			const data = {
				name: name,
				email: email,
				message: message,
			};
			fetch(endpoint, {
				method: 'POST',
				body: JSON.stringify(data),
			})
				.then((response) => {
					if (response.ok) {
						alert('Message sent successfully.');
						form.reset();
					} else {
						alert('An error occurred. Please try again later.');
					}
				})
				.catch(() => {
					alert('An error occurred. Please try again later.');
				});
		});
	},
	
};
</script>

<style scoped lang="scss">
.contact-section {
	background-color: #f1f1f1;
	padding: 50px 0;
	font-family: Avenir, Helvetica, Arial, sans-serif; 
}

.contact-container {
	max-width: 800px;
	margin: auto;
	text-align: center;
}

h2 {
	font-size: 2rem;
	margin-bottom: 30px;
}

form {
	display: flex;
	flex-direction: column;
	align-items: center;
}

label {
	display: block;
	margin-bottom: 10px;
	font-weight: bold;
}

input,
textarea {
	width: 100%;
	padding: 10px;
	margin-bottom: 20px;
	border-radius: 5px;
	border: none;
}

button {
	background-color: #4caf50;
	color: white;
	padding: 10px 20px;
	border: none;
	border-radius: 5px;
	cursor: pointer;
}

button:hover {
	background-color: #3e8e41;
}
</style>