<script>
    import fabricApiIcon from '$lib/assets/fabric-api.png';
    import meteorIcon from '$lib/assets/meteor.png';
    import uiUtilsIcon from '$lib/assets/ui-utils.png';
    import dupersIcon from '$lib/assets/dupers-united.png';
    import Icon from '@iconify/svelte';
</script>

<svelte:head>
    <title>DupersUnited - Mods for Duping</title>
    <meta name="description" content="Essential mods and tools for Minecraft dupe hunting. Meteor Client, UI Utils, and the DupersUnited Addon." />
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
                <a href="https://discord.gg/dupes" target="_blank" rel="noopener noreferrer" class="social-btn discord">
                    <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028 14.09 14.09 0 0 0 1.226-1.994.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/>
                    </svg>
                    Join Discord
                </a>

                <a class="social-btn home-btn" href="https://dupers.wtf" rel="noopener noreferrer" target="_blank">
                    <Icon height="24" icon="iconamoon:home-bold" width="24" />
                    Main site
                </a>
            </div>
        </header>
        
        <!-- Mods Grid -->
        <section class="mods-section">
            <h2 class="section-title">Essential Mods</h2>
            <div class="mods-grid">

                <!-- Fabric Api -->
                <div class="mod-card">
                    <div class="mod-icon">
                        <img alt="Fabric Api" src={fabricApiIcon} />
                    </div>
                    <div class="mod-info">
                        <h3 class="mod-name">Fabric Api</h3>
                        <p class="mod-description">
                            The base Api required for almost all Mods on Fabric!
                        </p>
                        <div class="mod-links">
                            <a class="mod-btn primary" href="https://modrinth.com/mod/fabric-api" rel="noopener noreferrer"
                               target="_blank">
                                <svg fill="none" height="18" stroke="currentColor" stroke-linecap="round"
                                     stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" width="18"
                                     xmlns="http://www.w3.org/2000/svg">
                                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                                    <polyline points="7 10 12 15 17 10"></polyline>
                                    <line x1="12" x2="12" y1="15" y2="3"></line>
                                </svg>
                                Download
                            </a>
                            <a class="mod-btn secondary" href="https://github.com/FabricMC/fabric-api" rel="noopener noreferrer"
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

                <!-- Meteor Client -->
                <div class="mod-card">
                    <div class="mod-icon">
                        <img src={meteorIcon} alt="Meteor Client" />
                    </div>
                    <div class="mod-info">
                        <h3 class="mod-name">Meteor Client</h3>
                        <p class="mod-description">
                            The base client for Minecraft utility mods. Required for the DupersUnited Addon.
                        </p>
                        <div class="mod-links">
                            <a href="https://meteorclient.com/" target="_blank" rel="noopener noreferrer" class="mod-btn primary">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                                    <polyline points="7 10 12 15 17 10"></polyline>
                                    <line x1="12" y1="15" x2="12" y2="3"></line>
                                </svg>
                                Download
                            </a>
                            <a href="https://github.com/MeteorDevelopment/meteor-client" target="_blank" rel="noopener noreferrer" class="mod-btn secondary">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
                                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                                </svg>
                                Source
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- UI Utils -->
                <div class="mod-card">
                    <div class="mod-icon">
                        <img src={uiUtilsIcon} alt="UI Utils" />
                    </div>
                    <div class="mod-info">
                        <h3 class="mod-name">UI Utils</h3>
                        <p class="mod-description">
                            Manipulate GUIs, close them without packets, save and load them, and much more.
                        </p>
                        <div class="mod-links">
                            <a href="https://www.curseforge.com/minecraft/mc-mods/uiutils" target="_blank" rel="noopener noreferrer" class="mod-btn primary">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                                    <polyline points="7 10 12 15 17 10"></polyline>
                                    <line x1="12" y1="15" x2="12" y2="3"></line>
                                </svg>
                                Download
                            </a>
                            <a href="https://github.com/Coderx-Gamer/ui-utils" target="_blank" rel="noopener noreferrer" class="mod-btn secondary">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
                                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                                </svg>
                                Source
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- DupersUnited Addon -->
                <div class="mod-card featured">
                    <div class="featured-badge">Our Addon</div>
                    <div class="mod-icon">
                        <img src={dupersIcon} alt="DupersUnited Public Addon" />
                    </div>
                    <div class="mod-info">
                        <h3 class="mod-name">DupersUnited Addon</h3>
                        <p class="mod-description">
                            A Meteor Addon with useful modules for dupe hunting. Requires Meteor Client.
                        </p>
                        <div class="mod-links">
                            <a href="/public-addon" class="mod-btn primary">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                                    <polyline points="7 10 12 15 17 10"></polyline>
                                    <line x1="12" y1="15" x2="12" y2="3"></line>
                                </svg>
                                Get Addon
                            </a>
                            <a href="https://github.com/YAYLOLDEV/du-addon-public" target="_blank" rel="noopener noreferrer" class="mod-btn secondary">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
                                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                                </svg>
                                Source
                            </a>
                        </div>
                    </div>
                </div>

                <!-- DupersUnited Resource Pack -->
                <div class="mod-card featured">
                    <div class="featured-badge">Our Resource Pack</div>
                    <div class="mod-icon">
                        <img alt="DupersUnited Resource Pack" src={dupersIcon} />
                    </div>
                    <div class="mod-info">
                        <h3 class="mod-name">DupersUnited Resource Pack</h3>
                        <p class="mod-description">
                            A Resource pack to Help with Dupe finding!
                        </p>
                        <div class="mod-links">
                            <a class="mod-btn primary" href="https://s-cdn.lolyay.dev/dps/du/DuResourcePack-v1.zip">
                                <svg fill="none" height="18" stroke="currentColor" stroke-linecap="round"
                                     stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" width="18"
                                     xmlns="http://www.w3.org/2000/svg">
                                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                                    <polyline points="7 10 12 15 17 10"></polyline>
                                    <line x1="12" x2="12" y1="15" y2="3"></line>
                                </svg>
                                Get Resource Pack
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Footer -->
        <footer class="footer">
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


    .social-btn.home-btn {
        background: linear-gradient(135deg, rgba(166, 88, 242, 0.2), rgba(166, 88, 242, 0.1));
        color: #a689da;
        border-color: rgba(166, 101, 242, 0.3);
    }

    .social-btn.home-btn:hover {
        background: linear-gradient(135deg, rgba(166, 101, 242, 0.3), rgba(166, 101, 242, 0.2));
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(166, 101, 242, 0.3);
    }

    .mods-section {
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
        
        .mod-card {
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        
        .mod-links {
            justify-content: center;
        }
    }
</style>