<script>
	export let colorBase;
	export let href;
</script>


<a class="btn" href={href} rel="noopener noreferrer" style="--button-hue: {colorBase}">

	<slot style="text-align: center; align-self: center; align-items: center;" />
</a>


<style>

    .btn {
        align-content: center;
        text-align: center;
        background: linear-gradient(135deg, rgba(var(--button-hue), 88, 242, 0.2), rgba(var(--button-hue), 88, 242, 0.1));
        color: rgba(var(--button-hue), 120, 242, 1);
        display: inline-flex;
        align-self: center;
        align-items: center;
        justify-content: center;
        gap: 0.5rem;
        padding: 0.875rem 1.5rem;
        border-radius: 12px;
        font-weight: 600;
        text-decoration: none;
        transition: all 0.3s ease;
        border: 1px solid rgba(var(--button-hue), 101, 242, 0.3);
    }

    .btn:hover {
        text-align: center;

        background: linear-gradient(135deg, rgba(var(--button-hue), 101, 242, 0.3), rgba(var(--button-hue), 101, 242, 0.2));
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(var(--button-hue), 101, 242, 0.3);
    }

</style>