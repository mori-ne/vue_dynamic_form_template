<script setup>
import {ref} from 'vue';

// 配列
const inputFields = ref([
	{
		id: 0,
		inputType: 'text',
		inputCode: 'code01',
		inputTitle: 'タイトル1',
		inputLabel: 'タイトルのサブラベルがはいります1',
		inputLimit: 100,
		inputPreviewCounter: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 1,
		inputType: 'textarea',
		inputCode: 'code02',
		inputTitle: 'タイトル2',
		inputLabel: 'タイトルのサブラベルがはいります2',
		inputLimit: 200,
		inputPreviewCounter: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 2,
		inputType: 'checkbox',
		inputCode: 'code03',
		inputTitle: 'タイトル3',
		inputLabel: 'タイトルのサブラベルがはいります3',
		inputLimit: 300,
		inputPreviewCounter: '',
		isChecked: false,
		isOpen: false,
	},
]);

// すべて開閉
const toggleAll = () => {
	const currentState = inputFields.value.every((field) => field.isOpen);
	inputFields.value.forEach((field) => {
		field.isOpen = !currentState;
	});
};

console.log(inputFields);
</script>

<template>
	<div class="max-w-7xl mx-auto px-8">
		<!-- トップ -->
		<div class="mt-8 mb-4">
			<div class="flex gap-4 border-b border-gray-300 pb-2">
				<p class="text-lg text-gray-900 font-bold">入力項目編集画面</p>
				<div class="ml-auto">
					<a href="#">フォームに戻る</a>
				</div>
			</div>
			<!-- プロジェクト・フォーム -->
			<div class="flex gap-4 pt-2">
				<div class="flex flex-row items-center">
					<p class="text-sm text-gray-400">プロジェクト名：</p>
					<h2 class="text-sm text-gray-900 font-bold">全国肢体不自由児学会</h2>
				</div>
				<div class="flex flex-row items-center">
					<p class="text-sm text-gray-400">フォーム名：</p>
					<h2 class="text-sm text-gray-900 font-bold">演題登録</h2>
				</div>
			</div>
		</div>

		<div class="max-w-7xl mx-auto flex flex-row bg-white border border-gray-300 rounded-lg overflow-hidden mb-14">
			<!-- セット項目 -->
			<div class="flex-shrink-0 bg-white w-80 border-r border-gray-300">
				<!-- タイトル -->
				<div class="text-gray-500 p-4 border-b border-gray-300">
					<h3 class="font-bold text-xl">セット項目</h3>
				</div>

				<div class="p-4 border-b border-gray-300">
					<select class="border rounded py-1 px-2 w-full mb-2" name="" id="">
						<option value="#">テキスト（1行）</option>
						<option value="#">テキストエリア（プレーン）</option>
						<option value="#">テキストエリア（リッチテキスト）</option>
						<option value="#">チェックリスト</option>
						<option value="#">ラジオボタン</option>
						<option value="#">見出し</option>
						<option value="#">段落</option>
						<option value="#">罫線</option>
					</select>
					<div class="flex justify-end gap-3">
						<button @click="toggleAll" type="button" class="text-sm text-gray-500">すべて開く/閉じる</button>
						<button class="rounded py-1 px-2 text-xs bg-gray-700 text-white" type="button">フィールドを追加</button>
					</div>
				</div>

				<ul>
					<li v-for="inputField in inputFields" :key="inputField.id" class="w-full border-b border-gray-300">
						<div class="flex flex-row justify-between items-center p-4">
							<p class="font-bold">テキスト（1行）</p>
							<!-- コントローラー -->
							<div class="ml-auto flex gap-2 items-center">
								<button id="up" type="button" class="text-sm"><i class="at-arrow-up-circle"></i></button>
								<button id="down" type="button" class="text-sm"><i class="at-arrow-down-circle"></i></button>
								<button id="delete" type="button" class="text-red-500 text-sm">削除</button>
								<button id="open" @click="inputField.isOpen = !inputField.isOpen" type="button" class="text-gray-500 text-sm">
									{{ inputField.isOpen ? '閉じる' : '開く' }}
								</button>
							</div>
						</div>

						<!-- detail -->
						<Transition>
							<div v-if="inputField.isOpen" id="detail" class="pl-4 pr-4">
								<div class="mb-2">
									<p class="text-xs text-gray-500 mb-1">タイトル</p>
									<input v-model="inputField.inputTitle" class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" placeholder="タイトル" />
								</div>
								<div class="mb-2">
									<p class="text-xs text-gray-500 mb-1">サブラベル</p>
									<input v-model="inputField.inputLabel" class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="サブラベルが入ります" />
								</div>
								<div class="mb-2">
									<p class="text-xs text-gray-500 mb-1">コード</p>
									<input v-model="inputField.inputCode" class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="コード" />
								</div>
								<div class="flex gap-4 pb-4">
									<div class="mb-2">
										<p class="text-xs text-gray-500 mb-1">文字数制限</p>
										<input v-model="inputField.inputLimit" class="border border-gray-300 rounded w-24 py-1 px-2 text-sm" type="number" placeholder="100" />
									</div>
									<div class="mb-2">
										<p class="text-xs text-gray-500 mb-1">必須</p>
										<input v-model="inputField.isChecked" class="w-4 h-4 border-gray-400 rounded" type="checkbox" name="required" value="必須" />
									</div>
								</div>
							</div>
						</Transition>
					</li>
				</ul>
			</div>

			<!-- プレビュー -->
			<div class="w-full mx-auto flex-initial bg-white">
				<div class="text-gray-500 p-4 border-b border-gray-300"><h3 class="font-bold text-xl">プレビュー</h3></div>

				<div class="max-w-4xl mx-auto p-8">
					<ul>
						<li v-for="inputField in inputFields" :key="inputField.id" class="mb-8">
							<div class="flex gap-2 items-center">
								<h4 class="font-bold text-lg">{{ inputField.inputTitle }}</h4>
								<p v-if="inputField.isChecked" class="bg-red-500 text-white text-xs inline-flex items-center justify-center py-0.5 px-2 rounded-full">必須</p>
							</div>
							<div class="flex justify-between mb-2">
								<p class="text-sm text-gray-400">{{ inputField.inputLabel }}</p>
								<p class="text-sm text-gray-900">{{ inputField.inputPreviewCounter.length }} / {{ inputField.inputLimit }}文字</p>
							</div>
							<textarea v-if="inputField.inputType == textarea" type="textarea"></textarea>
							<input v-model="inputField.inputPreviewCounter" class="w-full border rounded border-gray-300 p-2 mb-1" type="text" value="" />
							<div class="flex justify-end text-xs text-gray-400"><p v-text="inputField.inputCode"></p></div>
						</li>
					</ul>

					<!-- textarea -->
					<!-- <div class="mb-8">
						<div class="flex gap-2 items-center">
							<h4 class="font-bold text-lg">{{ inputTitle }}</h4>
							<p v-if="isChecked" class="bg-red-500 text-white text-xs inline-flex items-center justify-center py-0.5 px-2 rounded-full">必須</p>
						</div>
						<div class="flex justify-between mb-2">
							<p class="text-sm text-gray-400">{{ inputLabel }}</p>
							<p class="text-sm text-gray-900">{{ inputPreviewCounter.length }} / {{ inputLimit }}文字</p>
						</div>
						<textarea v-model="inputPreviewCounter" class="w-full border rounded border-gray-300 p-2 h-32" type="text" value="" />
						<div class="flex justify-end text-xs text-gray-400"><p v-text="inputCode"></p></div>
					</div> -->

					<!-- card -->
					<!-- <div class="mb-8">
						<div class="flex gap-2 items-center">
							<h4 class="font-bold text-lg">所属</h4>
						</div>
						<div class="flex justify-between mb-2">
							<p class="text-sm text-gray-400">所属機関名のサブラベルが入ります</p>
						</div>
						<div class="flex gap-5">
							<div class="flex gap-2">
								<input type="checkbox" name="" id="" />
								<label for="">医者</label>
							</div>
							<div class="flex gap-2">
								<input type="checkbox" name="" id="" />
								<label for="">研修医</label>
							</div>
							<div class="flex gap-2">
								<input type="checkbox" name="" id="" />
								<label for="">看護師</label>
							</div>
						</div>
					</div> -->

					<!-- card -->
					<!-- <div class="mb-8">
						<div class="flex gap-2 items-center">
							<h4 class="font-bold text-lg">カテゴリー</h4>
						</div>
						<div class="flex justify-between mb-2">
							<p class="text-sm text-gray-400">カテゴリーのサブラベルが入ります</p>
						</div>
						<div class="flex gap-5">
							<div class="flex gap-2">
								<input type="radio" name="radio" id="" />
								<label for="">コメディカル</label>
							</div>
							<div class="flex gap-2">
								<input type="radio" name="radio" id="" />
								<label for="">なんとかかんとか</label>
							</div>
							<div class="flex gap-2">
								<input type="radio" name="radio" id="" />
								<label for="">ああだこうだ</label>
							</div>
						</div>
					</div> -->

					<!-- <hr class="my-8 border-gray-300" /> -->
				</div>
			</div>
		</div>
	</div>

	<!-- ボトム -->
	<div class="fixed bottom-0 w-full border-t border-gray-300 bg-white">
		<div class="max-w-7xl mx-auto flex justify-end py-4 px-8">
			<button type="button" class="rounded text-md text-white bg-gray-700 font-bold px-4 py-1">更新する</button>
		</div>
	</div>
</template>

<style lang="css">
.v-enter-active,
.v-leave-active {
	transition: all 0.3s ease;
	overflow: hidden;
}
.v-enter-from,
.v-leave-to {
	height: 0;
}
.v-enter-to,
.v-leave-from {
	height: 250px;
}
</style>
