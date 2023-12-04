<script lang="ts">
	import Vertical from './lib/components/vertical.svelte'
	import { Presentation, Slide, Media } from '@components'
	import { animate, signal } from '@motion'
	import Number from './number.svelte'
	import Stack from '@lib/components/stack.svelte'
	import Code from '@lib/components/code.svelte'

	const code1 =
		'border p-[0] rounded-md leading-[-1em] bg-gray-800 h-[.3em] text-3xl'

	const style1 = 'text-4xl text-gray-400 my-3'
	const style2 = 'text-4xl text-white font-bold mr-5 my-3'

</script>

<Presentation>
	<Slide animate>
		<div class="font-bold text-8xl flex justify-center">
			<Media
				type="img"
				class="h-[6rem] w-[6rem]"
				src="https://leetcode.com/static/images/LeetCode_logo_rvs.png"
			/>
			<p>LeetCode</p>
		</div>
		<p>by Johnnnyツ</p>
	</Slide>

	<Vertical>
		<Slide animate>
			<div class="font-bold text-8xl flex justify-center">
				<Media
					type="img"
					class="h-[6rem] w-[6rem]"
					src="https://leetcode.com/static/images/LeetCode_logo_rvs.png"
				/>
				<p>LeetCode</p>
			</div>
			<p>#315</p>
		</Slide>
		<Slide animate>
			<p class="text-5xl">#315</p>
			<p>
				<span class="text-red-600">Hard:</span> Count of Smaller Numbers After Self
			</p>
		</Slide>
	</Vertical>

	<Vertical>
		<Slide>
			<p class="leading-[1.3em]">
				Given an integer array <span class={code1}>nums</span> , return an
				integer array <span class={code1}>counts</span> where
				<span class={code1}>counts[i]</span>
				is the number of smaller elements to the right of
				<span class={code1}>nums[i]</span> .
			</p>
		</Slide>
		<Slide>
			<p>
				ให้นับจำนวนตัวที่น้อยกว่า ที่อยู่หลังจาก index นั้นๆแล้วเก็บเป็น array
			</p>
		</Slide>
		<Slide>
			<div class="text-left">
				<p class={`${style2} italic mb-8 text-5xl`}>Example:</p>
				<p class={style1}><span class={style2}>Input:</span>nums = [5,2,6,1]</p>
				<p class={style1}><span class={style2}>Output:</span> [2,1,1,0]</p>
				<p class={style2}>Explanation:</p>
				<div class='text-2xl'>
					<ul class='list-disc list-inside'>
						<li>ตัวหลังจาก 5 มีตัวที่เล็กกว่า 2 ตัวคือ (2 และ 1)</li>
						<li>ตัวหลังจาก 2 มีตัวที่เล็กกว่า 1 ตัวคือ (1)</li>
						<li>ตัวหลังจาก 6 มีตัวที่เล็กกว่า 1 ตัวคือ (1)</li>
						<li>ตัวหลังจาก 1 ไม่มีตัวที่เล็กกว่า จึงเป็น 0</li>
					</ul>
				</div>
			</div>
		</Slide>
	</Vertical>

	<Vertical>
		<Slide animate>
			<Code lang="js" lines="1-12|2,3|4,10|5-8|5,9|11">
				{`
					var countSmaller = function (nums) {
						const n = nums.length;
						let counts = []
						for (let i = 0; i < n; i++) { // loop i
							let count = 0
							for (let j = i + 1; j < n; j++) { // loop j ตัวที่หลังจาก i 
								if (nums[i] > nums[j]) count++  // หาตัวที่น้อยกว่าตำแหน่ง i แล้วนับ
							}
						counts[i] = count
						}
					return counts 
					}
				`}
			</Code>
		</Slide>
		<Slide animate>
			<h1 class="font-bold text-8xl">Finish</h1>

		</Slide>
	</Vertical>

</Presentation>
