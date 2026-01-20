<script>
	export let href;
</script>


<a class="btn" href={href} rel="noopener noreferrer">
	<slot />
</a>


<style>
    .btn {
        background: linear-gradient(135deg, rgba(var(--button-hue), 88, 242, 0.2), rgba(var(--button-hue), 88, 242, 0.1));
        color: rgba(var(--button-hue), 120, 242, 1);
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.875rem 1.5rem;
        border-radius: 12px;
        font-weight: 600;
        text-decoration: none;
        transition: all 0.3s ease;
        border: 1px solid rgba(var(--button-hue), 101, 242, 0.3);
    }

    .btn {
        background: linear-gradient(135deg, #8b5cf6 0%, #6366f1 100%);
        color: white;
        box-shadow: 0 4px 15px rgba(139, 92, 246, 0.3);
    }

    .btn:hover {
        background: linear-gradient(135deg, #a78bfa 0%, #818cf8 100%);
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(139, 92, 246, 0.4);
    }

</style>