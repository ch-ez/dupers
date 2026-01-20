<script>
	import fabricApiIcon from '$lib/assets/fabric-api.png';
	import meteorIcon from '$lib/assets/meteor.png';
	import uiUtilsIcon from '$lib/assets/ui-utils.png';
	import dupersIcon from '$lib/assets/dupers-united.png';
	import Icon from '@iconify/svelte';
	import GlassButton from '$lib/components/btn/GlassButton.svelte';
	import ModCard from '$lib/components/cards/ModCard.svelte';
</script>

<svelte:head>
	<title>DupersUnited - Mods for Duping</title>
	<meta
		content="Essential mods and tools for Minecraft dupe hunting. Meteor Client, UI Utils, and the DupersUnited Addon."
		name="description" />
	<link href="https://fonts.googleapis.com" rel="preconnect">
	<link crossorigin href="https://fonts.gstatic.com" rel="preconnect">
	<link
		href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@500;600&display=swap"
		rel="stylesheet">
</svelte:head>

<div class="page-wrapper">
	<main class="container">
		<!-- Hero Section -->
		<header class="hero">
			<div class="logo-container">
				<div class="logo-glow"></div>
				<h1 class="title">
					<span class="title-accent">Dupers</span>United
				</h1>
			</div>
			<p class="subtitle">Mods for Duping</p>
			<p class="description">
				Everything you need to start dupe hunting in Minecraft.
			</p>

			<div class="social-links">
				<GlassButton colorBase="88" href="https://discord.gg/dupes">
					<svg fill="currentColor" height="22" viewBox="0 0 24 24" width="22" xmlns="http://www.w3.org/2000/svg">
						<path
							d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028 14.09 14.09 0 0 0 1.226-1.994.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z" />
					</svg>
					Join Discord
				</GlassButton>

				<GlassButton colorBase="166" href="https://dupers.wtf">
					<Icon height="24" icon="iconamoon:home-bold" width="24" />
					Main site
				</GlassButton>
			</div>
		</header>

		<!-- Mods Grid -->
		<section class="partner-section">
			<h2 class="section-title">Essential Mods</h2>
			<div class="mods-grid">

				<!-- Fabric Api -->
				<ModCard
					description="Fabric Api is needed for almost all Mods!"
					downloadUrl="https://modrinth.com/mod/fabric-api#download"
					iconUrl={fabricApiIcon}
					name="Fabric Api"
					sourceUrl="https://github.com/FabricMC/fabric-api"
				/>


				<!-- Meteor Client -->

				<ModCard
					description="The base client for Minecraft utility mods. Required for the DupersUnited Addon."
					downloadUrl="https://meteorclient.com/"
					iconUrl={meteorIcon}
					name="Meteor Client"
					sourceUrl="https://github.com/MeteorDevelopment/meteor-client"
				/>


				<!-- UI Utils -->

				<ModCard
					description="Manipulate GUIs, close them without packets, save and load them, and more."
					downloadUrl="https://www.curseforge.com/minecraft/mc-mods/uiutils"
					iconUrl={uiUtilsIcon}
					name="Ui Utils"
					sourceUrl="https://github.com/Coderx-Gamer/ui-utils"
				/>


				<!-- DupersUnited Addon -->

				<ModCard
					description="A Meteor Addon with useful Modules and Commands for dupe hunting."
					downloadUrl="/public-addon"
					iconUrl={dupersIcon}
					isDu=true
					name="DupersUnited Addon"
					sourceUrl="https://github.com/YAYLOLDEV/DupersUnited"
				/>
				<!-- DupersUnited Resource Pack -->

				<ModCard
					description="A Resource pack to Help with Dupe finding!"
					downloadUrl="https://s-cdn.lolyay.dev/dps/du/DuResourcePack-v1.zip"
					duModInfo="Resource Pack"
					iconUrl={dupersIcon}
					isDu=true
					name="DupersUnited Pack"
				/>
			</div>
		</section>

		<!-- Footer -->
		<footer class="footer">
			<p class="copyright">© 2026 DupersUnited. All rights reserved.</p>
		</footer>
	</main>
</div>

<style>
    .container {
        position: relative;
        z-index: 1;
        max-width: 1200px;
        margin: 0 auto;
        padding: 3rem 1.5rem;
    }

    .hero {
        text-align: center;
        padding: 4rem 0;
    }

    .logo-container {
        position: relative;
        display: inline-block;
        margin-bottom: 1rem;
    }

    .logo-glow {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 300px;
        height: 100px;
        background: radial-gradient(ellipse, rgba(139, 92, 246, 0.3) 0%, transparent 70%);
        filter: blur(30px);
        pointer-events: none;
    }

    .title {
        position: relative;
        font-size: clamp(2.5rem, 8vw, 4.5rem);
        font-weight: 800;
        letter-spacing: -0.02em;
        background: linear-gradient(135deg, #ffffff 0%, #e0e0e0 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }

    .title-accent {
        background: linear-gradient(135deg, #a78bfa 0%, #8b5cf6 50%, #6366f1 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }

    .subtitle {
        font-size: 1.25rem;
        font-weight: 500;
        color: rgba(255, 255, 255, 0.6);
        margin-bottom: 1.5rem;
        text-transform: uppercase;
        letter-spacing: 0.2em;
    }

    .description {
        max-width: 600px;
        margin: 0 auto 2rem;
        font-size: 1.1rem;
        line-height: 1.7;
        color: rgba(255, 255, 255, 0.7);
    }

    .social-links {
        display: flex;
        justify-content: center;
        gap: 1rem;
        flex-wrap: wrap;
    }

    .partner-section {
        margin-top: 2rem;
    }

    .section-title {
        text-align: center;
        font-size: 1.75rem;
        font-weight: 700;
        margin-bottom: 2.5rem;
        background: linear-gradient(135deg, #ffffff 0%, rgba(255, 255, 255, 0.7) 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }

    .mods-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
        gap: 1.5rem;
    }


    .footer {
        margin-top: 6rem;
        text-align: center;
        padding: 2rem 0;
        border-top: 1px solid rgba(255, 255, 255, 0.1);
    }

    .copyright {
        font-size: 0.8rem;
        color: rgba(255, 255, 255, 0.3);
    }

    @media (max-width: 768px) {
        .container {
            padding: 2rem 1rem;
        }

        .hero {
            padding: 2rem 0;
        }

        .mods-grid {
            grid-template-columns: 1fr;
        }
    }
</style>