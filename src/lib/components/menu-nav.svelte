<script lang="ts">
	import ButtonIcon from './button-icon.svelte';
	let activeTab = 'Home';
	const tabs = [
		{ name: 'Home', icon: '/icons/home.svg', activeIcon: '/icons/home-active.svg' },
		{ name: 'Messages', icon: '/icons/message.svg', activeIcon: '/icons/message-active.svg' },
		{ name: 'Help', icon: '/icons/help.svg', activeIcon: '/icons/help-active.svg' }
	];
	function setActiveTab(name: string) {
		activeTab = name;
	}
</script>

{#each tabs as tab}
	<ButtonIcon
		{activeTab}
		tabName={tab.name}
		iconSrc={tab.icon}
		activeIconSrc={tab.activeIcon}
		onClick={() => setActiveTab(tab.name)}
	/>
{/each}
