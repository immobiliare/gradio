<script lang="ts">
	import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
	import StaticImage from "./Index.svelte";
</script>

<Meta
	title="Components/Image"
	component={Image}
	argTypes={{
		value: {
			control: "object",
			description: "The image URL or file to display",
			name: "value",
			value: {
				name: "https://i.ibb.co/6BgKdSj/groot.jpg",
				is_file: true,
				data: null
			}
		},
		show_download_button: {
			options: [true, false],
			description: "If false, the download button will not be visible",
			control: { type: "boolean" },
			defaultValue: true
		}
	}}
/>

<Template let:args>
	<div
		class="image-container"
		style="width: 300px; position: relative;border-radius: var(--radius-lg);overflow: hidden;"
	>
		<StaticImage {...args} />
	</div>
</Template>

<Story
	name="Static Image with label and download button"
	args={{
		value: {
			name: "https://i.ibb.co/6BgKdSj/groot.jpg",
			is_file: true,
			data: null
		},
		show_label: true,
		show_download_button: true
	}}
/>

<Story
	name="Static Image with no label or download button"
	args={{
		value: {
			name: "https://i.ibb.co/6BgKdSj/groot.jpg",
			is_file: true,
			data: null
		},
		show_label: false,
		show_download_button: false
	}}
/>
