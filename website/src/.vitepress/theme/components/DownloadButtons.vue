<script setup lang="ts">
import { computed, onMounted, ref } from "vue"
import { data as release } from "../data/release.data"

const downloadInformation = computed(() => ({
	preview: {
		tagName: release.preview.tag_name ?? "r0000",
		asset: (release.preview.assets ?? [])
			.find((a) => /^tachiyomi-r\d{4,}.apk/.test(a.name)),
	},
	stable: {
		tagName: release.stable.tag_name?.slice(1) ?? "0.00.0",
		asset: (release.stable.assets ?? [])
			.find((a) => /^tachiyomi-v\d+\.\d+\.\d+.apk/.test(a.name)),
	},
}))

const isAndroid = ref(true)

onMounted(() => {
	isAndroid.value = !!navigator.userAgent.match(/android/i)
})
</script>

<template>
	<div>
		<div v-if="!isAndroid" class="custom-block danger">
			<p class="custom-block-title">
				Unsupported Operating System
			</p>
			<p>
				<strong>Tachiyomi</strong> is an <strong>Android app</strong> only.
				Use an <strong>Android device</strong> to download and install the app.
			</p>
		</div>
		<div v-if="!isAndroid" class="custom-block warning">
			<p class="custom-block-title">
				Caution
			</p>
			<p>
				Any app for other operating systems that are not Android and
				that calls itself <strong>Tachiyomi</strong> is
				<strong>impersonating</strong> the original
				<strong>Tachiyomi</strong> app for <strong>Android</strong>
				and is not affiliated with the project.
			</p>
			<blockquote>
				For more information, read the
				<a href="/docs/faq/general">General FAQ</a>.
			</blockquote>
		</div>
		<div class="download-buttons">
			<a class="download-button primary" :download="downloadInformation.stable.asset?.name" :href="downloadInformation.stable.asset?.browser_download_url">
				<IconDownload />
				<span class="text">Stable</span>
				<span class="version">{{ downloadInformation.stable.tagName }}</span>
			</a>
			<a class="download-button secondary" :download="downloadInformation.preview.asset?.name" :href="downloadInformation.preview.asset?.browser_download_url">
				<IconBugReport />
				<span class="text">Preview</span>
				<span class="version">{{ downloadInformation.preview.tagName }}</span>
			</a>
		</div>
		<span class="version-disclaimer">
			Requires <strong>Android 6.0</strong> or higher.
		</span>
	</div>
</template>

<style lang="stylus">
.download-buttons {
	display: flex
	gap: 0.75em
	justify-content: center
	align-items: center
	margin: 0.75em auto
}

.download-button {
	display: inline-block
	border: 1px solid transparent
	text-align: center
	font-weight: 600
	white-space: nowrap
	transition: color 0.25s, border-color 0.25s, background-color 0.25s
	cursor: pointer
	transition: all 0.3s ease
	border-radius: 20px
	padding: 0 20px
	line-height: 38px
	font-size: 14px

	&:hover {
		text-decoration: none !important
	}

	&.primary {
		border-color: var(--vp-button-brand-border)
		color: var(--vp-button-brand-text)
		background-color: var(--vp-button-brand-bg)

		&:hover {
			border-color: var(--vp-button-brand-hover-border)
			color: var(--vp-button-brand-hover-text)
			background-color: var(--vp-button-brand-hover-bg)
		}

		&:active {
			border-color: var(--vp-button-brand-active-border)
			color: var(--vp-button-brand-active-text)
			background-color: var(--vp-button-brand-active-bg)
		}
	}

	&.secondary {
		border-color: var(--vp-button-alt-border)
		color: var(--vp-button-alt-text)
		background-color: var(--vp-button-alt-bg)

		&:hover {
			border-color: var(--vp-button-alt-hover-border)
			color: var(--vp-button-alt-hover-text)
			background-color: var(--vp-button-alt-hover-bg)
		}

		&:active {
			border-color: var(--vp-button-alt-active-border)
			color: var(--vp-button-alt-active-text)
			background-color: var(--vp-button-alt-active-bg)
		}
	}

	svg {
		display: inline-block
		vertical-align: middle
		margin-right: 0.5em
		font-size: 1.25em
	}

	.text {
		margin-right: 10px
	}

	.version {
		font-size: 0.8em
	}
}

.version-disclaimer {
	display: block
	text-align: center
	margin: 0.75em auto
	font-size: 0.75rem
}
</style>
