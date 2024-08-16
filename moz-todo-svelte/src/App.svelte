<script>
	import { onMount } from 'svelte';
	import Writeups from './Writeups.svelte';
	import Resources from './Resources.svelte';

	let activePage = 'about'; // default active page

	// Function to set active page based on the section clicked
	function setActive(page) {
		activePage = page;
	}
</script>

<main>
	<div class="top-bar">
		<div class="left_col">
			<img src="/favicon.png" alt="Team Icon" class="team-icon">
			<span class="team-name">Coconut Phishers</span>
		</div>
		<div class="right_col">
			<nav>
				<a href="#about" class:active={activePage === 'about'} on:click={() => setActive('about')}>About</a>
				<a href="#writeups" class:active={activePage === 'writeups'} on:click={() => setActive('writeups')}>Writeups</a>
				<a href="#resources" class:active={activePage === 'resources'} on:click={() => setActive('resources')}>Resources</a>
				<a href="#contact" class:active={activePage === 'contact'} on:click={() => setActive('contact')}>Contact</a>
			</nav>
		</div>
	</div>

	<div class="content">
		{#if activePage === 'about'}
			<section class="intro">
				<h1>Cyber Security Enthusiasts from IIIT-H</h1>
				<p>
					We are <span class="highlight">Coconut Phishers</span>, a passionate team of cybersecurity enthusiasts from <span class="highlight">IIIT-Hyderabad</span>. 
					Our student-run team is at the forefront of 
					creating a vibrant cybersecurity environment on campus, where we mentor the next generation of cybersecurity professionals.
				</p>
				<p>
					At <span class="highlight">Coconut Phishers</span>, we actively participate in numerous CTFs and organize events and trainings. Our mission is to foster a culture of cybersecurity awareness and excellence within our college and beyond.
				</p>
			</section>
		{:else if activePage === 'writeups'}
			<Writeups />
		{:else if activePage === 'resources'}
			<Resources />
		{:else if activePage === 'contact'}
			<!-- Add content for the Contact page here -->
		{/if}
	</div>
</main>

<style>
	@font-face {
		font-family: 'Orb-Thick';
		src: url('/Orbitron-Black.ttf') format('truetype');
		font-weight: normal;
		font-style: normal;
	}

	@font-face {
		font-family: 'Orb-Thin';
		src: url('/Orbitron-Regular.ttf') format('truetype');
		font-weight: normal;
		font-style: normal;
	}

	:global(body) {
		margin: 0;
		padding: 0;
		background-image: url('/bgd.jpg');
		background-size: cover;
		background-position: center;
		color: #FFFAFA;
		font-family: 'Orb-Thick';
	}

	:global(html, body) {
		height: 100%;
	}

	:global(#app) {
		height: 100%;
		display: flex;
		flex-direction: column;
	}

	main {
		display: flex;
		flex-direction: column;
		width: 100%;
		height: 100%;
		backdrop-filter: blur(1px);
		background-color: rgba(24, 20, 43, 0.8); /* Deep indigo background */
	}

	.top-bar {
		display: flex;
		width: 100%;
		background-color: rgba(68, 51, 103, 0.7); /* Rich purple background */
		padding: 15px 20px;
		box-sizing: border-box;
		backdrop-filter: blur(5px);
	}

	.left_col, .right_col {
		flex: 1;
		display: flex;
		align-items: center;
	}

	.left_col {
		justify-content: flex-start;
		font-size: small;
	}

	.right_col {
		justify-content: flex-end;
		font-size: large;
	}

	nav a {
		color: #FFF1E6; /* Soft cream color */
		text-decoration: none;
		margin: 0 15px;
		font-weight: bold;
		transition: color 0.3s ease;
	}

	nav a:hover {
		color: #FFB86C; /* Warm peach hover color */
	}

	nav a.active {
		color: #FF79C6; /* Vibrant pink color for active link */
		text-decoration: underline;
	}

	.team-icon {
		height: 50px;
		margin-right: 10px;
	}

	.team-name {
		font-size: x-large;
		font-weight: bold;
		color: #FF79C6; /* Vibrant pink color */
	}

	.content {
		flex: 1;
		padding: 20px;
		color: #F8F8F2; /* Soft light gray */
		box-sizing: border-box;
		overflow-y: auto;
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
		font-family: 'Orb-Thin';
	}

	.intro {
		max-width: 1000px;
		height: 500px;
		background-color: rgba(68, 51, 103, 0.7); /* Muted plum background for intro section */
	}

	h1 {
		font-size: 2.0em;
		margin-bottom: 60px;
		color: #FF79C6; /* Vibrant pink color */
	}

	p {
		font-size: 1.25em;
		line-height: 1.6;
		margin-bottom: 60px;
		margin-left: 50px;
		margin-right: 50px;
		color: #FFF1E6; /* Soft cream color */
	}

	.highlight {
		color: #FFB86C; /* Warm peach color for highlights */
		font-weight: bold;
	}
</style>
