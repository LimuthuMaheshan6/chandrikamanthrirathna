<script lang="ts">
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	
	let isMenuOpen = false;
	let isScrolled = false;

	onMount(() => {
		const handleScroll = () => {
			isScrolled = window.scrollY > 20;
		};
		window.addEventListener('scroll', handleScroll);
		return () => window.removeEventListener('scroll', handleScroll);
	});

	function toggleMenu() {
		isMenuOpen = !isMenuOpen;
	}

	function closeMenu() {
		isMenuOpen = false;
	}
</script>

<nav class="navbar" class:scrolled={isScrolled}>
	<div class="nav-container">
		<a href="/" class="logo" aria-label="Home">
			<img src="medi_banner.png" width="60" alt=""/>
			<span class="logo-text">Chandrika </span>
		</a>

		<button class="menu-toggle" aria-label="Toggle menu" on:click={toggleMenu}>
			<span class="hamburger" class:active={isMenuOpen}></span>
		</button>

		<ul class="nav-links" class:active={isMenuOpen}>
			<li>
				<a href="/" class:active={$page.url.pathname === '/'} on:click={closeMenu}>
					Home
				</a>
			</li>
			<li>
				<a href="/skills" class:active={$page.url.pathname === '/skills'} on:click={closeMenu}>
					Skills
				</a>
			</li>
			<li>
				<a href="/projects" class:active={$page.url.pathname === '/projects'} on:click={closeMenu}>
					Projects
				</a>
			</li>
			<li>
				<a href="/education" class:active={$page.url.pathname === '/education'} on:click={closeMenu}>
					Education
				</a>
			</li>
			<li>
				<a href="/contact" class:active={$page.url.pathname === '/contact'} on:click={closeMenu}>
					Contact
				</a>
			</li>
		</ul>
	</div>
</nav>

<style>
	.navbar {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		background: rgba(255, 255, 255, 0.95);
		backdrop-filter: blur(10px);
		z-index: 1000;
		transition: all 0.3s ease;
		border-bottom: 1px solid transparent;
	}

	.navbar.scrolled {
		box-shadow: var(--shadow-md);
		border-bottom-color: var(--border-color);
	}

	.nav-container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 1rem 1.5rem;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.logo {
		display: flex;
		align-items: center;
		gap: 0.75rem;
		font-weight: 700;
		font-size: 1.25rem;
		color: var(--primary-color);
		transition: transform 0.2s ease;
	}

	.logo:hover {
		transform: scale(1.05);
	}

	.logo-text {
		display: none;
	}

	@media (min-width: 640px) {
		.logo-text {
			display: inline;
		}
	}

	.nav-links {
		display: flex;
		list-style: none;
		gap: 2rem;
		align-items: center;
	}

	.nav-links a {
		font-weight: 500;
		color: var(--text-primary);
		position: relative;
		padding: 0.5rem 0;
		transition: color 0.2s ease;
	}

	.nav-links a:hover,
	.nav-links a.active {
		color: var(--primary-color);
	}

	.nav-links a.active::after {
		content: '';
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		height: 2px;
		background: var(--primary-color);
	}

	.menu-toggle {
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 30px;
		height: 30px;
		background: none;
		border: none;
		cursor: pointer;
		padding: 0;
	}

	.hamburger {
		width: 25px;
		height: 2px;
		background: var(--text-primary);
		transition: all 0.3s ease;
		position: relative;
	}

	.hamburger::before,
	.hamburger::after {
		content: '';
		position: absolute;
		width: 25px;
		height: 2px;
		background: var(--text-primary);
		transition: all 0.3s ease;
	}

	.hamburger::before {
		top: -8px;
		left: 0;
	}

	.hamburger::after {
		bottom: -8px;
		left: 0;
	}

	.hamburger.active {
		background: transparent;
	}

	.hamburger.active::before {
		top: 0;
		transform: rotate(45deg);
	}

	.hamburger.active::after {
		bottom: 0;
		transform: rotate(-45deg);
	}

	@media (max-width: 768px) {
		.menu-toggle {
			display: flex;
		}

		.nav-links {
			position: fixed;
			top: 70px;
			left: 0;
			right: 0;
			background: white;
			flex-direction: column;
			padding: 2rem;
			gap: 1.5rem;
			box-shadow: var(--shadow-lg);
			transform: translateX(-100%);
			transition: transform 0.3s ease;
			align-items: flex-start;
		}

		.nav-links.active {
			transform: translateX(0);
		}

		.nav-links a {
			font-size: 1.125rem;
			width: 100%;
		}
	}

	@media (min-width: 769px) {
		.menu-toggle {
			display: none;
		}
	}
</style>

