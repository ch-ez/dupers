<script>
    import { page } from '$app/stores';
</script>

<svelte:head>
    <title>404 - Page Not Found | DupersUnited</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
</svelte:head>

<div class="error-page">
    <div class="bg-gradient"></div>
    <div class="floating-orbs">
        <div class="orb orb-1"></div>
        <div class="orb orb-2"></div>
    </div>
    
    <div class="content">
        <div class="glitch-container">
            <h1 class="error-code" data-text="404">404</h1>
        </div>
        
        <div class="glass-card">
            <h2 class="title">Lost in the Void</h2>
            <p class="message">
                The page you're looking for doesn't exist or has been moved to another dimension.
            </p>
            
            <a href="/" class="home-btn">
                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path>
                    <polyline points="9 22 9 12 15 12 15 22"></polyline>
                </svg>
                Back to Home
            </a>
        </div>
        
        <div class="particles">
            {#each Array(20) as _, i}
                <div class="particle" style="--delay: {i * 0.5}s; --x: {Math.random() * 100}%; --duration: {3 + Math.random() * 4}s;"></div>
            {/each}
        </div>
    </div>
</div>

<style>
    :global(body) {
        font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
        background: #0a0a0f;
        color: #ffffff;
        margin: 0;
        padding: 0;
        min-height: 100vh;
        overflow-x: hidden;
    }
    
    .error-page {
        position: relative;
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 2rem;
    }
    
    .bg-gradient {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background: 
            radial-gradient(ellipse at top, rgba(239, 68, 68, 0.15) 0%, transparent 50%),
            radial-gradient(ellipse at bottom, rgba(139, 92, 246, 0.1) 0%, transparent 50%);
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
    }
    
    .orb {
        position: absolute;
        border-radius: 50%;
        filter: blur(80px);
        animation: float 15s ease-in-out infinite;
    }
    
    .orb-1 {
        width: 300px;
        height: 300px;
        background: rgba(239, 68, 68, 0.2);
        top: 20%;
        left: 10%;
    }
    
    .orb-2 {
        width: 250px;
        height: 250px;
        background: rgba(139, 92, 246, 0.15);
        bottom: 20%;
        right: 15%;
        animation-delay: -7s;
    }
    
    @keyframes float {
        0%, 100% { transform: translate(0, 0) scale(1); }
        50% { transform: translate(30px, -30px) scale(1.1); }
    }
    
    .content {
        position: relative;
        z-index: 1;
        text-align: center;
    }
    
    .glitch-container {
        position: relative;
        margin-bottom: 2rem;
    }
    
    .error-code {
        font-size: clamp(6rem, 20vw, 12rem);
        font-weight: 800;
        margin: 0;
        background: linear-gradient(135deg, #ef4444 0%, #f97316 50%, #a855f7 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        position: relative;
        animation: glitch 3s infinite;
        text-shadow: none;
    }
    
    .error-code::before,
    .error-code::after {
        content: attr(data-text);
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(135deg, #ef4444 0%, #f97316 50%, #a855f7 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
    
    .error-code::before {
        animation: glitch-1 2s infinite;
        clip-path: polygon(0 0, 100% 0, 100% 45%, 0 45%);
    }
    
    .error-code::after {
        animation: glitch-2 2s infinite;
        clip-path: polygon(0 55%, 100% 55%, 100% 100%, 0 100%);
    }
    
    @keyframes glitch-1 {
        0%, 100% { transform: translate(0); }
        20% { transform: translate(-3px, 3px); }
        40% { transform: translate(3px, -3px); }
        60% { transform: translate(-3px, -3px); }
        80% { transform: translate(3px, 3px); }
    }
    
    @keyframes glitch-2 {
        0%, 100% { transform: translate(0); }
        20% { transform: translate(3px, -3px); }
        40% { transform: translate(-3px, 3px); }
        60% { transform: translate(3px, 3px); }
        80% { transform: translate(-3px, -3px); }
    }
    
    .glass-card {
        background: rgba(30, 30, 40, 0.6);
        backdrop-filter: blur(20px);
        -webkit-backdrop-filter: blur(20px);
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 24px;
        padding: 2.5rem 3rem;
        max-width: 450px;
        margin: 0 auto;
    }
    
    .title {
        font-size: 1.75rem;
        font-weight: 700;
        margin: 0 0 1rem;
        background: linear-gradient(135deg, #ffffff 0%, #a78bfa 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
    
    .message {
        color: rgba(255, 255, 255, 0.6);
        font-size: 1rem;
        line-height: 1.6;
        margin: 0 0 2rem;
    }
    
    .home-btn {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        background: linear-gradient(135deg, #8b5cf6 0%, #6366f1 100%);
        color: white;
        padding: 1rem 2rem;
        border-radius: 12px;
        font-weight: 600;
        text-decoration: none;
        transition: all 0.3s ease;
        box-shadow: 0 4px 20px rgba(139, 92, 246, 0.4);
    }
    
    .home-btn:hover {
        transform: translateY(-3px);
        box-shadow: 0 8px 30px rgba(139, 92, 246, 0.5);
    }
    
    .particles {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        pointer-events: none;
        z-index: 0;
    }
    
    .particle {
        position: absolute;
        width: 4px;
        height: 4px;
        background: rgba(168, 85, 247, 0.5);
        border-radius: 50%;
        left: var(--x);
        bottom: -10px;
        animation: rise var(--duration) ease-in-out infinite;
        animation-delay: var(--delay);
    }
    
    @keyframes rise {
        0% {
            transform: translateY(0) scale(1);
            opacity: 0;
        }
        10% {
            opacity: 1;
        }
        90% {
            opacity: 1;
        }
        100% {
            transform: translateY(-100vh) scale(0);
            opacity: 0;
        }
    }
    
    @media (max-width: 480px) {
        .glass-card {
            padding: 2rem 1.5rem;
        }
    }
</style>
