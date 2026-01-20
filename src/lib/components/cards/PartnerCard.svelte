<script>
	export let name;
	export let tag;
	export let iconUrl;
	export let clickUrl;
</script>

<a class="partner-card" href="{clickUrl}" target="_blank">
	<div class="icon-badge">
		<slot name="icon" />
	</div>

	<div class="profile-icon">
		<img alt={name} src={iconUrl} />
	</div>
	<div class="profile-info">
		<h3 class="profile-name">{name}</h3>
		<h3 class="profile-tag">{tag}</h3>
	</div>

</a>

<style>
    .partner-card {
        text-decoration: none;
        cursor: pointer;
        position: relative;
        display: flex;
        gap: 1.5rem;
        padding: 1.75rem;
        background: linear-gradient(135deg, rgba(139, 92, 246, 0.15), rgba(99, 102, 241, 0.08));
        backdrop-filter: blur(20px);
        border: 1px solid rgba(139, 92, 246, 0.3);
        border-radius: 20px;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        overflow: hidden;
    }

    .partner-card::before {
        content: '';
        position: absolute;
        inset: 0;
        background: linear-gradient(135deg, rgba(167, 139, 250, 0.1) 0%, transparent 50%);
        opacity: 0;
        transition: opacity 0.3s ease;
        pointer-events: none;
    }

    .partner-card:hover::before {
        opacity: 1;
    }

    .partner-card:hover {
        transform: translateY(-4px);
        border-color: rgba(167, 139, 250, 0.5);
        box-shadow: 0 20px 40px -15px rgba(139, 92, 246, 0.4),
        0 0 30px rgba(139, 92, 246, 0.15);
    }

    .profile-tag {
        font-size: 0.9rem;
        line-height: 1.5;
        color: rgba(167, 139, 250, 0.8);
        margin: 0;
        transition: color 0.3s ease;
    }

    .partner-card:hover .profile-tag {
        color: rgba(196, 181, 253, 1);
    }

    .icon-badge {
        position: absolute;
        right: 0.75rem;
        top: 0.75rem;
        color: white;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .profile-icon {
        flex-shrink: 0;
        width: 72px;
        height: 72px;
        border-radius: 16px;
        overflow: hidden;
        background: linear-gradient(135deg, rgba(139, 92, 246, 0.2), rgba(99, 102, 241, 0.1));

        transition: all 0.3s ease;
    }

    .partner-card:hover .profile-icon {
        border-color: rgba(167, 139, 250, 0.5);
        box-shadow: 0 0 20px rgba(139, 92, 246, 0.3);
    }

    .profile-icon img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: transform 0.3s ease;
    }

    .partner-card:hover .profile-icon img {
        transform: scale(1.05);
    }

    .profile-info {
        flex: 1;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        justify-content: center;
    }

    .profile-name {
        font-size: 1.25rem;
        font-weight: 700;
        margin: 0;
        background: linear-gradient(135deg, #ffffff 0%, #e0e0e0 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        transition: all 0.3s ease;
    }

    .partner-card:hover .profile-name {
        background: linear-gradient(135deg, #a78bfa 0%, #c4b5fd 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
</style>