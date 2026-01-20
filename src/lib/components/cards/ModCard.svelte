<script>
	export let name;
	export let description;
	export let iconUrl;
	export let isDu = false;
	export let duModInfo = 'Addon';
	export let downloadUrl = '#';
	export let sourceUrl = '#';
</script>

<div class="mod-card" class:featured={isDu}>
	{#if isDu}
		<div class="featured-badge">Our {duModInfo}</div>
	{/if}
	<div class="mod-icon">
		<img alt={name} src={iconUrl} />
	</div>
	<div class="mod-info">
		<h3 class="mod-name">{name}</h3>
		<p class="mod-description">
			{description}
		</p>
		<div class="mod-links">
			<a class="mod-btn primary" href={downloadUrl}
				 rel="noopener noreferrer"
				 target={!isDu ? '_blank' : '_self'}
			>
				<svg fill="none" height="18" stroke="currentColor" stroke-linecap="round"
						 stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" width="18"
						 xmlns="http://www.w3.org/2000/svg">
					<path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
					<polyline points="7 10 12 15 17 10"></polyline>
					<line x1="12" x2="12" y1="15" y2="3"></line>
				</svg>
				Download
			</a>
			<a class="mod-btn secondary" href={sourceUrl}
				 rel="noopener noreferrer"
				 target="_blank">
				<svg fill="currentColor" height="18" viewBox="0 0 24 24" width="18"
						 xmlns="http://www.w3.org/2000/svg">
					<path
						d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z" />
				</svg>
				Source
			</a>
		</div>
	</div>
</div>

<style>
    .mod-card {
        position: relative;
        display: flex;
        gap: 1.5rem;
        padding: 1.75rem;
        background: rgba(30, 30, 40, 0.6);
        backdrop-filter: blur(20px);
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 20px;
        transition: all 0.3s ease;
    }

    .mod-card:hover {
        transform: translateY(-5px);
        border-color: rgba(139, 92, 246, 0.3);
        box-shadow: 0 20px 50px -15px rgba(0, 0, 0, 0.5);
    }

    .mod-card.featured {
        border-color: rgba(139, 92, 246, 0.3);
        background: linear-gradient(135deg, rgba(139, 92, 246, 0.1), rgba(30, 30, 40, 0.6));
    }

    .featured-badge {
        position: absolute;
        top: -10px;
        right: 20px;
        background: linear-gradient(135deg, #8b5cf6 0%, #6366f1 100%);
        color: white;
        padding: 0.4rem 1rem;
        border-radius: 20px;
        font-size: 0.75rem;
        font-weight: 600;
        text-transform: uppercase;
        letter-spacing: 0.05em;
    }

    .mod-icon {
        flex-shrink: 0;
        width: 72px;
        height: 72px;
        border-radius: 16px;
        overflow: hidden;
        background: rgba(255, 255, 255, 0.05);
    }

    .mod-icon img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .mod-info {
        flex: 1;
        display: flex;
        flex-direction: column;
        gap: 0.75rem;
    }

    .mod-name {
        font-size: 1.25rem;
        font-weight: 700;
        color: #ffffff;
        margin: 0;
    }

    .mod-description {
        font-size: 0.9rem;
        line-height: 1.5;
        color: rgba(255, 255, 255, 0.6);
        margin: 0;
    }

    .mod-links {
        display: flex;
        gap: 0.75rem;
        margin-top: auto;
        flex-wrap: wrap;
    }

    .mod-btn {
        display: inline-flex;
        align-items: center;
        gap: 0.4rem;
        padding: 0.6rem 1rem;
        border-radius: 10px;
        font-size: 0.85rem;
        font-weight: 600;
        text-decoration: none;
        transition: all 0.2s ease;
    }

    .mod-btn.primary {
        background: linear-gradient(135deg, #8b5cf6 0%, #6366f1 100%);
        color: white;
    }

    .mod-btn.primary:hover {
        transform: translateY(-2px);
        box-shadow: 0 5px 20px rgba(139, 92, 246, 0.4);
    }

    .mod-btn.secondary {
        background: rgba(255, 255, 255, 0.1);
        color: rgba(255, 255, 255, 0.8);
        border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .mod-btn.secondary:hover {
        background: rgba(255, 255, 255, 0.15);
        transform: translateY(-2px);
    }
</style>