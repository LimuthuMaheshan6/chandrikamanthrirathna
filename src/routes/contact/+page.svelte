<script lang="ts">
	interface FormData {
		name: string;
		email: string;
		phone: string;
		subject: string;
		message: string;
	}
	
	let formData: FormData = {
		name: '',
		email: '',
		phone: '',
		subject: '',
		message: ''
	};

	let isSubmitting = false;
	let submitStatus: 'idle' | 'success' | 'error' = 'idle';
	let submitMessage = '';

	async function handleSubmit(e: Event) {
		e.preventDefault();
		isSubmitting = true;
		submitStatus = 'idle';
		submitMessage = '';

		// Simulate form submission (replace with actual API call)
		try {
			await new Promise(resolve => setTimeout(resolve, 1000));
			
			// In a real application, you would send this to your backend
			console.log('Form submitted:', formData);
			
			submitStatus = 'success';
			submitMessage = 'Thank you for your message! I will get back to you soon.';
			
			// Reset form
			formData = {
				name: '',
				email: '',
				phone: '',
				subject: '',
				message: ''
			};
		} catch (error) {
			submitStatus = 'error';
			submitMessage = 'There was an error sending your message. Please try again.';
		} finally {
			isSubmitting = false;
		}
	}
</script>

<div class="contact-page">
	

	<section class="section" style="padding-bottom: 150px;">
		<div class="container">
			<div class="contact-grid">
				<div class="contact-info">
					<h2 class="section-title">Contact Information</h2>
					<p class="info-text">
						Whether you're looking for a dedicated healthcare professional, have a project in mind, 
						or simply want to connect, I'm here to help.
					</p>

					<div class="contact-methods">
						<div class="contact-method">
							<div class="method-icon">
								<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
									<path d="M3 8L10.89 13.26C11.2187 13.4793 11.6049 13.5963 12 13.5963C12.3951 13.5963 12.7813 13.4793 13.11 13.26L21 8M5 19H19C19.5304 19 20.0391 18.7893 20.4142 18.4142C20.7893 18.0391 21 17.5304 21 17V7C21 6.46957 20.7893 5.96086 20.4142 5.58579C20.0391 5.21071 19.5304 5 19 5H5C4.46957 5 3.96086 5.21071 3.58579 5.58579C3.21071 5.96086 3 6.46957 3 7V17C3 17.5304 3.21071 18.0391 3.58579 18.4142C3.96086 18.7893 4.46957 19 5 19Z" stroke="#2563eb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
								</svg>
							</div>
							<div>
								<h3>Email</h3>
								<a href="mailto:contact@nurseportfolio.com">macmanthrirathna@gmail.com</a>
							</div>
						</div>

						<div class="contact-method">
							<div class="method-icon">
								<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
									<path d="M3 5C3 3.89543 3.89543 3 5 3H8.27924C8.70967 3 9.09181 3.27543 9.22792 3.68377L10.7257 8.17721C10.8831 8.64932 10.6694 9.16531 10.2243 9.38787L7.96701 10.5165C9.06925 12.9612 11.0388 14.9308 13.4835 16.033L14.6121 13.7757C14.8347 13.3306 15.3507 13.1169 15.8228 13.2743L20.3162 14.7721C20.7246 14.9082 21 15.2903 21 15.7208V19C21 20.1046 20.1046 21 19 21H18C9.71573 21 3 14.2843 3 6V5Z" stroke="#2563eb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
								</svg>
							</div>
							<div>
								<h3>Phone</h3>
								<a href="tel:+94702795428">0702795428</a>
							</div>
						</div>

						<div class="contact-method">
							<div class="method-icon">
								<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
									<path d="M21 10C21 17 12 23 12 23C12 23 3 17 3 10C3 7.61305 3.94821 5.32387 5.63604 3.63604C7.32387 1.94821 9.61305 1 12 1C14.3869 1 16.6761 1.94821 18.364 3.63604C20.0518 5.32387 21 7.61305 21 10Z" stroke="#2563eb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
									<circle cx="12" cy="10" r="3" stroke="#2563eb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
								</svg>
							</div>
							<div>
								<h3>520/2, Punchi Mandawala, Mandawala</h3>
								
							</div>
						</div>
					</div>
				</div>

			</div>
		</div>
	</section>

	<section class="hero-small section">
		<div class="container">
			<h1 class="page-title">Get In Touch</h1>
			<p class="page-subtitle">I'd love to hear from you. Let's start a conversation.</p>
		</div>
	</section>
</div>

<style>
	.contact-page {
		padding-top: 70px;
	}

	.hero-small {
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		color: white;
		text-align: center;
		padding: 4rem 0;
	}

	.page-title {
		font-size: 3rem;
		font-weight: 800;
		margin-bottom: 1rem;
	}

	.page-subtitle {
		font-size: 1.25rem;
		opacity: 0.95;
	}

	.contact-grid {
		
		align-items: center;
	}

	.section-title {
		font-size: 2.5rem;
		font-weight: 700;
		margin-bottom: 1.5rem;
		color: var(--text-primary);
	}

	.info-text {
		color: var(--text-secondary);
		line-height: 1.7;
		margin-bottom: 2.5rem;
		font-size: 1.125rem;
	}

	.contact-methods {
		display: flex;
		flex-direction: column;
		gap: 2rem;
	}

	.contact-method {
		display: flex;
		gap: 1.5rem;
		align-items: flex-start;
	}

	.method-icon {
		flex-shrink: 0;
		width: 48px;
		height: 48px;
		background: var(--bg-secondary);
		border-radius: 0.75rem;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.contact-method h3 {
		font-size: 1.125rem;
		font-weight: 600;
		margin-bottom: 0.5rem;
		color: var(--text-primary);
	}

	.contact-method a {
		color: var(--primary-color);
		font-weight: 500;
		transition: color 0.2s ease;
	}

	.contact-method a:hover {
		color: var(--primary-dark);
	}

	.contact-method p {
		color: var(--text-secondary);
	}

	.contact-form-wrapper {
		background: white;
		padding: 2.5rem;
		border-radius: 1rem;
		box-shadow: var(--shadow-md);
	}

	.contact-form {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}

	.form-group {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.form-group label {
		font-weight: 600;
		color: var(--text-primary);
		font-size: 0.9375rem;
	}

	.form-group input,
	.form-group textarea {
		padding: 0.875rem 1rem;
		border: 2px solid var(--border-color);
		border-radius: 0.5rem;
		font-family: inherit;
		font-size: 1rem;
		transition: border-color 0.2s ease;
		background: var(--bg-primary);
	}

	.form-group input:focus,
	.form-group textarea:focus {
		outline: none;
		border-color: var(--primary-color);
	}

	.form-group textarea {
		resize: vertical;
		min-height: 120px;
	}

	.alert {
		padding: 1rem;
		border-radius: 0.5rem;
		display: flex;
		align-items: center;
		gap: 0.75rem;
		font-weight: 500;
	}

	.alert-success {
		background: #d1fae5;
		color: #065f46;
	}

	.alert-error {
		background: #fee2e2;
		color: #991b1b;
	}

	.btn {
		padding: 0.875rem 2rem;
		border-radius: 0.5rem;
		font-weight: 600;
		transition: all 0.3s ease;
		display: inline-block;
		font-size: 1rem;
		background: var(--primary-color);
		color: white;
		width: 100%;
	}

	.btn:hover:not(:disabled) {
		background: var(--primary-dark);
		transform: translateY(-2px);
		box-shadow: var(--shadow-md);
	}

	.btn:disabled {
		opacity: 0.6;
		cursor: not-allowed;
	}

	.btn-large {
		padding: 1.125rem 2.5rem;
		font-size: 1.125rem;
	}

	@media (max-width: 968px) {
		.contact-grid {
			grid-template-columns: 1fr;
			gap: 3rem;
		}
	}

	@media (max-width: 768px) {
		.page-title {
			font-size: 2.25rem;
		}

		.contact-form-wrapper {
			padding: 1.5rem;
		}
	}
</style>

