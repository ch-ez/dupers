<script>
    import VersionCard from '$lib/components/VersionCard.svelte';
    import { onMount } from 'svelte';
    
    const mcVersions = ['1.21.4', '1.21.8', '1.21.10', '1.21.11'];
    
    let latestModVersion = 'v1.0.0';
    let modVersionClean = '1.0.0';
    let contributors = [];
    
    const manualContributors = [
        {
            login: 'KhaoDoesDev',
            html_url: 'https://github.com/Khao',
            avatar_url: 'https://avatars.githubusercontent.com/u/62739017?v=4',
            contributions: 1
        }
    ];
    
    onMount(async () => {
        try {
            const [releaseRes, contribRes] = await Promise.all([
                fetch('https://api.github.com/repos/YAYLOLDEV/du-addon-public/releases/latest'),
                fetch('https://api.github.com/repos/YAYLOLDEV/du-addon-public/contributors')
            ]);
            
            if (releaseRes.ok) {
                const data = await releaseRes.json();
                latestModVersion = data.tag_name || 'v1.0.0';
                modVersionClean = latestModVersion.replace(/^v/, '');
            }
            
            if (contribRes.ok) {
                const ghContributors = await contribRes.json();
                contributors = [
                    ...ghContributors.filter(c => c.login !== 'YAYLOLDEV'),
                    ...manualContributors
                ];
            }
        } catch (e) {
            console.log('Could not fetch data from GitHub');
            contributors = manualContributors;
        }
    });
    
    $: downloadUrls = Object.fromEntries(
        mcVersions.map(v => [v, `https://github.com/YAYLOLDEV/du-addon-public/releases/latest/download/dupersunited-public-addon-${v}-${modVersionClean}.jar`])
    );
</script>

<svelte:head>
    <title>DupersUnited Public Addon</title>
    <meta name="description" content="Download the DupersUnited Public Addon for Minecraft. Available for multiple versions." />
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@500;600&display=swap" rel="stylesheet">
</svelte:head>

<div class="page-wrapper">
    <div class="bg-gradient"></div>
    <div class="bg-grid"></div>
    <div class="floating-orbs">
        <div class="orb orb-1"></div>
        <div class="orb orb-2"></div>
        <div class="orb orb-3"></div>
    </div>
    
    <main class="container">
        <a href="/" class="back-link">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <polyline points="15 18 9 12 15 6"></polyline>
            </svg>
            Back to Mods List
        </a>
        
        <header class="hero">
            <a href="https://dupers.wtf" class="logo-container" target="_blank" rel="noopener noreferrer">
                <div class="logo-glow"></div>
                <h1 class="title">
                    <span class="title-accent">Dupers</span>United
                </h1>
            </a>
            <p class="subtitle">Public Addon</p>
            <p class="description">
                The ultimate enhancement for your Minecraft experience. 
                Choose your version below and start exploring.
            </p>
            
            <div class="social-links">
                <a href="https://discord.gg/dupes" target="_blank" rel="noopener noreferrer" class="social-btn discord">
                    <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028 14.09 14.09 0 0 0 1.226-1.994.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/>
                    </svg>
                    Join Discord
                </a>
                <a href="#versions" class="social-btn download">
                    <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                        <polyline points="7 10 12 15 17 10"></polyline>
                        <line x1="12" y1="15" x2="12" y2="3"></line>
                    </svg>
                    Download
                </a>
                <a href="https://github.com/YAYLOLDEV/du-addon-public" target="_blank" rel="noopener noreferrer" class="social-btn github">
                    <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                    </svg>
                    Source Code
                </a>
            </div>
        </header>
        
        <section class="meta-row">
            <div class="callout-card">
                <div class="callout-left">
                    <div class="callout-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <circle cx="12" cy="12" r="10"></circle>
                            <line x1="12" y1="8" x2="12" y2="12"></line>
                            <line x1="12" y1="16" x2="12.01" y2="16"></line>
                        </svg>
                    </div>
                    <p>Found a bug or have a feature request?</p>
                </div>
                <a href="https://github.com/YAYLOLDEV/du-addon-public/issues/new" target="_blank" rel="noopener noreferrer" class="callout-btn">
                    <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                        <polyline points="15 3 21 3 21 9"></polyline>
                        <line x1="10" y1="14" x2="21" y2="3"></line>
                    </svg>
                    Open Issue
                </a>
            </div>
            
            {#if contributors.length > 0}
            <div class="contributors-inline">
                <span class="contributors-label">Contributors:</span>
                <div class="contributors-avatars">
                    {#each contributors as contributor}
                        <a href={contributor.html_url} target="_blank" rel="noopener noreferrer" class="contributor-mini">
                            <img src={contributor.avatar_url} alt={contributor.login} />
                            <div class="contributor-tooltip">
                                <span class="tooltip-name">{contributor.login}</span>
                                <span class="tooltip-commits">{contributor.contributions} {contributor.contributions === 1 ? 'commit' : 'commits'}</span>
                            </div>
                        </a>
                    {/each}
                </div>
            </div>
            {/if}
        </section>
        
        <section id="versions" class="versions-section">
            <h2 class="section-title">Available Versions</h2>
            <div class="versions-grid">
                {#each mcVersions as mcVersion}
                    <VersionCard 
                        mcVersion={mcVersion} 
                        modVersion={latestModVersion}
                        downloadUrl={downloadUrls[mcVersion]}
                    />
                {/each}
            </div>
        </section>
        
        <footer class="footer">
            <p>
                Want to build it yourself? Check out the 
                <a href="https://github.com/YAYLOLDEV/du-addon-public" target="_blank" rel="noopener noreferrer">
                    source code on GitHub
                </a>
            </p>
            <p class="copyright">© 2026 DupersUnited. All rights reserved.</p>
        </footer>
    </main>
</div>

<style>
    :global(*) {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    
    :global(body) {
        font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
        background: #0a0a0f;
        color: #ffffff;
        min-height: 100vh;
        overflow-x: hidden;
        scrollbar-width: none;
        -ms-overflow-style: none;
    }
    
    :global(body::-webkit-scrollbar) {
        display: none;
    }
    
    .page-wrapper {
        position: relative;
        min-height: 100vh;
    }
    
    .bg-gradient {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background: 
            radial-gradient(ellipse at top left, rgba(139, 92, 246, 0.15) 0%, transparent 50%),
            radial-gradient(ellipse at bottom right, rgba(59, 130, 246, 0.1) 0%, transparent 50%),
            radial-gradient(ellipse at center, rgba(99, 102, 241, 0.05) 0%, transparent 70%);
        pointer-events: none;
        z-index: 0;
    }
    
    .bg-grid {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-image: 
            linear-gradient(rgba(255, 255, 255, 0.02) 1px, transparent 1px),
            linear-gradient(90deg, rgba(255, 255, 255, 0.02) 1px, transparent 1px);
        background-size: 50px 50px;
        pointer-events: none;
        z-index: 0;
    }
    
    .floating-orbs {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        pointer-events: none;
        z-index: 0;
        overflow: hidden;
    }
    
    .orb {
        position: absolute;
        border-radius: 50%;
        filter: blur(80px);
        animation: float 20s ease-in-out infinite;
    }
    
    .orb-1 {
        width: 400px;
        height: 400px;
        background: rgba(139, 92, 246, 0.2);
        top: -100px;
        right: -100px;
        animation-delay: 0s;
    }
    
    .orb-2 {
        width: 300px;
        height: 300px;
        background: rgba(59, 130, 246, 0.15);
        bottom: 10%;
        left: -50px;
        animation-delay: -7s;
    }
    
    .orb-3 {
        width: 250px;
        height: 250px;
        background: rgba(168, 85, 247, 0.1);
        top: 50%;
        right: 20%;
        animation-delay: -14s;
    }
    
    @keyframes float {
        0%, 100% { transform: translate(0, 0) scale(1); }
        25% { transform: translate(30px, -30px) scale(1.05); }
        50% { transform: translate(-20px, 20px) scale(0.95); }
        75% { transform: translate(20px, 30px) scale(1.02); }
    }
    
    .container {
        position: relative;
        z-index: 1;
        max-width: 1200px;
        margin: 0 auto;
        padding: 2rem 1.5rem;
    }
    
    .back-link {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        color: rgba(255, 255, 255, 0.6);
        text-decoration: none;
        font-size: 0.9rem;
        transition: color 0.2s ease;
        margin-bottom: 1rem;
    }
    
    .back-link:hover {
        color: #a78bfa;
    }
    
    .hero {
        text-align: center;
        padding: 3rem 0;
    }
    
    .logo-container {
        position: relative;
        display: inline-block;
        margin-bottom: 1rem;
        text-decoration: none;
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
    
    .social-btn {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.875rem 1.5rem;
        border-radius: 12px;
        font-weight: 600;
        text-decoration: none;
        transition: all 0.3s ease;
        border: 1px solid transparent;
    }
    
    .social-btn.discord {
        background: linear-gradient(135deg, rgba(88, 101, 242, 0.2), rgba(88, 101, 242, 0.1));
        color: #7289da;
        border-color: rgba(88, 101, 242, 0.3);
    }
    
    .social-btn.discord:hover {
        background: linear-gradient(135deg, rgba(88, 101, 242, 0.3), rgba(88, 101, 242, 0.2));
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(88, 101, 242, 0.3);
    }
    
    .social-btn.github {
        background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
        color: #ffffff;
        border-color: rgba(255, 255, 255, 0.2);
    }
    
    .social-btn.github:hover {
        background: linear-gradient(135deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.1));
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(255, 255, 255, 0.1);
    }
    
    .social-btn.download {
        background: linear-gradient(135deg, #8b5cf6 0%, #6366f1 100%);
        color: white;
        box-shadow: 0 4px 15px rgba(139, 92, 246, 0.3);
    }
    
    .social-btn.download:hover {
        background: linear-gradient(135deg, #a78bfa 0%, #818cf8 100%);
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(139, 92, 246, 0.4);
    }
    
    .versions-section, .partners-section {
        margin-top: 4rem;
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
    
    .versions-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        gap: 1.5rem;
    }
    
    .partners-grid {
        display: flex;
        justify-content: center;
        gap: 1.5rem;
        flex-wrap: wrap;
    }
    
    .partner-card {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1rem;
        padding: 1.5rem 2rem;
        background: rgba(30, 30, 40, 0.6);
        backdrop-filter: blur(20px);
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 16px;
        text-decoration: none;
        transition: all 0.3s ease;
        min-width: 160px;
    }
    
    .partner-card:hover {
        transform: translateY(-5px);
        border-color: rgba(139, 92, 246, 0.3);
        box-shadow: 0 15px 40px -10px rgba(0, 0, 0, 0.4);
    }
    
    .partner-icon {
        width: 64px;
        height: 64px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 12px;
        flex-shrink: 0;
    }
    
    .partner-icon.youtube {
        background: linear-gradient(135deg, rgba(255, 0, 0, 0.2), rgba(255, 0, 0, 0.1));
        color: #ff0000;
    }
    
    .partner-icon.shop {
        background: linear-gradient(135deg, rgba(34, 197, 94, 0.2), rgba(34, 197, 94, 0.1));
        color: #22c55e;
    }
    
    .partner-name {
        color: rgba(255, 255, 255, 0.9);
        font-weight: 600;
        font-size: 0.95rem;
    }
    
    .meta-row {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 2rem;
        margin-top: 1.5rem;
        flex-wrap: wrap;
    }
    
    .callout-card {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 0.75rem;
        padding: 0.6rem 1rem;
        background: linear-gradient(135deg, rgba(251, 191, 36, 0.1), rgba(245, 158, 11, 0.05));
        border: 1px solid rgba(251, 191, 36, 0.3);
        border-radius: 10px;
        flex: 1;
    }
    
    .callout-icon {
        flex-shrink: 0;
        width: 28px;
        height: 28px;
        display: flex;
        align-items: center;
        justify-content: center;
        background: rgba(251, 191, 36, 0.2);
        border-radius: 6px;
        color: #fbbf24;
    }
    
    .callout-left {
        display: flex;
        align-items: center;
        gap: 0.75rem;
    }
    
    .callout-left p {
        color: rgba(255, 255, 255, 0.8);
        font-weight: 500;
        font-size: 0.8rem;
        margin: 0;
        white-space: nowrap;
    }
    
    .callout-btn {
        display: inline-flex;
        align-items: center;
        gap: 0.3rem;
        padding: 0.35rem 0.6rem;
        background: rgba(251, 191, 36, 0.2);
        color: #fbbf24;
        border: 1px solid rgba(251, 191, 36, 0.3);
        border-radius: 6px;
        font-size: 0.75rem;
        font-weight: 600;
        text-decoration: none;
        transition: all 0.2s ease;
        white-space: nowrap;
    }
    
    .callout-btn:hover {
        background: rgba(251, 191, 36, 0.3);
    }
    
    .contributors-inline {
        display: flex;
        align-items: center;
        gap: 0.75rem;
    }
    
    .contributors-label {
        color: rgba(255, 255, 255, 0.5);
        font-size: 0.8rem;
        font-weight: 500;
    }
    
    .contributors-avatars {
        display: flex;
        gap: 0.4rem;
    }
    
    .contributor-mini {
        position: relative;
        display: block;
        width: 32px;
        height: 32px;
        border-radius: 50%;
        overflow: visible;
        border: 2px solid rgba(139, 92, 246, 0.3);
        transition: all 0.2s ease;
    }
    
    .contributor-mini:hover {
        transform: scale(1.1);
        border-color: rgba(139, 92, 246, 0.6);
    }
    
    .contributor-mini img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 50%;
    }
    
    .contributor-tooltip {
        position: absolute;
        bottom: calc(100% + 8px);
        left: 50%;
        transform: translateX(-50%);
        background: rgba(20, 20, 30, 0.95);
        backdrop-filter: blur(10px);
        border: 1px solid rgba(139, 92, 246, 0.3);
        border-radius: 8px;
        padding: 0.5rem 0.75rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.2rem;
        opacity: 0;
        visibility: hidden;
        transition: all 0.2s ease;
        pointer-events: none;
        white-space: nowrap;
        z-index: 100;
    }
    
    .contributor-tooltip::after {
        content: '';
        position: absolute;
        top: 100%;
        left: 50%;
        transform: translateX(-50%);
        border: 6px solid transparent;
        border-top-color: rgba(139, 92, 246, 0.3);
    }
    
    .contributor-mini:hover .contributor-tooltip {
        opacity: 1;
        visibility: visible;
    }
    
    .tooltip-name {
        color: #fff;
        font-weight: 600;
        font-size: 0.8rem;
    }
    
    .tooltip-commits {
        color: rgba(167, 139, 250, 0.9);
        font-size: 0.7rem;
    }
    
    .contributors-section {
        margin-top: 2rem;
    }
    
    .section-title-sm {
        text-align: center;
        font-size: 1.25rem;
        font-weight: 600;
        margin-bottom: 1.5rem;
        color: rgba(255, 255, 255, 0.7);
    }
    
    .contributors-grid {
        display: flex;
        justify-content: center;
        gap: 1.5rem;
        flex-wrap: wrap;
    }
    
    .contributor-card {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.5rem;
        padding: 0.75rem 1rem;
        background: rgba(30, 30, 40, 0.5);
        backdrop-filter: blur(20px);
        border: 1px solid rgba(255, 255, 255, 0.08);
        border-radius: 12px;
        text-decoration: none;
        transition: all 0.3s ease;
        min-width: 100px;
    }
    
    .contributor-card:hover {
        transform: translateY(-3px);
        border-color: rgba(139, 92, 246, 0.3);
        box-shadow: 0 10px 30px -10px rgba(0, 0, 0, 0.4);
    }
    
    .contributor-avatar {
        width: 40px;
        height: 40px;
        border-radius: 50%;
        border: 2px solid rgba(139, 92, 246, 0.3);
    }
    
    .contributor-name {
        color: rgba(255, 255, 255, 0.9);
        font-weight: 600;
        font-size: 0.8rem;
    }
    
    .contributor-commits {
        color: rgba(255, 255, 255, 0.5);
        font-size: 0.7rem;
    }
    
    .footer {
        margin-top: 6rem;
        text-align: center;
        padding: 2rem 0;
        border-top: 1px solid rgba(255, 255, 255, 0.1);
    }
    
    .home-site-link {
        display: inline-block;
        font-size: 1.25rem;
        font-weight: 700;
        color: #a78bfa;
        text-decoration: none;
        margin-bottom: 1rem;
        transition: color 0.2s ease;
    }
    
    .home-site-link:hover {
        color: #c4b5fd;
    }
    
    .footer p {
        color: rgba(255, 255, 255, 0.5);
        font-size: 0.9rem;
        margin-bottom: 0.5rem;
    }
    
    .footer a {
        color: #a78bfa;
        text-decoration: none;
        transition: color 0.2s ease;
    }
    
    .footer a:hover {
        color: #c4b5fd;
        text-decoration: underline;
    }
    
    .copyright {
        font-size: 0.8rem !important;
        color: rgba(255, 255, 255, 0.3) !important;
    }
    
    @media (max-width: 768px) {
        .container {
            padding: 1.5rem 1rem;
        }
        
        .hero {
            padding: 2rem 0;
        }
        
        .social-links {
            flex-direction: column;
            align-items: center;
        }
        
        .social-btn {
            width: 100%;
            max-width: 250px;
            justify-content: center;
        }
        
        .partners-grid {
            flex-direction: column;
            align-items: center;
        }
        
        .partner-card {
            width: 100%;
            max-width: 250px;
        }
    }
</style>
