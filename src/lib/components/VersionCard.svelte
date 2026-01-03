<script>
    export let mcVersion;
    export let modVersion = 'Loading...';
    export let downloadUrl = '#';
</script>

<div class="version-card">
    <div class="card-glow"></div>
    <div class="card-content">
        <div class="minecraft-badge">
            <span class="mc-version">Minecraft {mcVersion}</span>
        </div>
        
        <div class="mod-info">
            <h3 class="mod-title">DupersUnited Addon</h3>
            <div class="version-row">
                <div class="version-tag">
                    <span class="version-label">Mod Version</span>
                    <span class="version-number">{modVersion}</span>
                </div>
                <div class="version-tag mc">
                    <span class="version-label">Minecraft Version</span>
                    <span class="version-number mc-num">{mcVersion}</span>
                </div>
            </div>
        </div>
        
        <a href={downloadUrl} target="_blank" rel="noopener noreferrer" class="download-btn">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                <polyline points="7 10 12 15 17 10"></polyline>
                <line x1="12" y1="15" x2="12" y2="3"></line>
            </svg>
            Download
        </a>
    </div>
</div>

<style>
    .version-card {
        position: relative;
        background: rgba(30, 30, 40, 0.6);
        backdrop-filter: blur(20px);
        -webkit-backdrop-filter: blur(20px);
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 16px;
        padding: 1.25rem;
        transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        overflow: hidden;
    }
    
    .version-card::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        height: 1px;
        background: linear-gradient(90deg, 
            transparent, 
            rgba(139, 92, 246, 0.5), 
            rgba(59, 130, 246, 0.5), 
            transparent
        );
    }
    
    .version-card:hover {
        transform: translateY(-5px);
        border-color: rgba(139, 92, 246, 0.3);
        box-shadow: 
            0 20px 40px -12px rgba(0, 0, 0, 0.5),
            0 0 40px -15px rgba(139, 92, 246, 0.3);
    }
    
    .card-glow {
        position: absolute;
        top: -50%;
        left: -50%;
        width: 200%;
        height: 200%;
        background: radial-gradient(
            circle at center,
            rgba(139, 92, 246, 0.1) 0%,
            transparent 50%
        );
        opacity: 0;
        transition: opacity 0.4s ease;
        pointer-events: none;
    }
    
    .version-card:hover .card-glow {
        opacity: 1;
    }
    
    .card-content {
        position: relative;
        z-index: 1;
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    
    .minecraft-badge {
        display: inline-flex;
        align-items: center;
        gap: 0.4rem;
        background: linear-gradient(135deg, rgba(34, 197, 94, 0.2), rgba(22, 163, 74, 0.1));
        border: 1px solid rgba(34, 197, 94, 0.3);
        padding: 0.35rem 0.75rem;
        border-radius: 50px;
        width: fit-content;
    }
    
    .mc-version {
        font-size: 0.8rem;
        font-weight: 600;
        color: #4ade80;
        text-shadow: 0 0 10px rgba(74, 222, 128, 0.3);
    }
    
    .mod-info {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }
    
    .mod-title {
        font-size: 1.1rem;
        font-weight: 700;
        background: linear-gradient(135deg, #fff 0%, #a78bfa 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        margin: 0;
    }
    
    .version-row {
        display: flex;
        gap: 1.5rem;
    }
    
    .version-tag {
        display: flex;
        flex-direction: column;
        gap: 0.15rem;
    }
    
    .version-number.mc-num {
        color: #4ade80;
    }
    
    .version-label {
        font-size: 0.65rem;
        text-transform: uppercase;
        letter-spacing: 0.1em;
        color: rgba(255, 255, 255, 0.5);
    }
    
    .version-number {
        font-size: 0.95rem;
        font-weight: 600;
        color: #c4b5fd;
        font-family: 'JetBrains Mono', 'Fira Code', monospace;
    }
    
    .download-btn {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        gap: 0.4rem;
        background: linear-gradient(135deg, #8b5cf6 0%, #6366f1 100%);
        color: white;
        padding: 0.65rem 1rem;
        border-radius: 10px;
        font-weight: 600;
        font-size: 0.9rem;
        text-decoration: none;
        transition: all 0.3s ease;
        box-shadow: 0 4px 15px rgba(139, 92, 246, 0.3);
    }
    
    .download-btn svg {
        width: 16px;
        height: 16px;
    }
    
    .download-btn:hover {
        background: linear-gradient(135deg, #a78bfa 0%, #818cf8 100%);
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(139, 92, 246, 0.4);
    }
    
    .download-btn:active {
        transform: translateY(0);
    }
</style>
