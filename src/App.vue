<script setup>
import {ref} from 'vue';

// 配列
const inputFields = ref([
	{
		id: 0,
		inputType: 'text',
		inputCode: 'code01',
		inputTitle: 'テキスト（1行）',
		inputLabel: 'テキスト（1行）のサブラベルがはいります1',
		inputLimit: 100,
		inputContent: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 1,
		inputType: 'textarea',
		inputCode: 'code02',
		inputTitle: 'テキストエリア（標準）',
		inputLabel: 'テキストエリア（標準）のサブラベルがはいります2',
		inputLimit: 200,
		inputContent: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 2,
		inputType: 'textarea_rtf',
		inputCode: 'code03',
		inputTitle: 'テキストエリア（RTF）',
		inputLabel: 'テキストエリア（RTF）のサブラベルがはいります3',
		inputLimit: 300,
		inputContent: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 3,
		inputType: 'checkbox',
		inputCode: 'code03',
		inputTitle: 'チェックボックス',
		inputLabel: 'チェックボックスのサブラベルがはいります3',
		inputLimit: 300,
		inputContent: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 4,
		inputType: 'radio',
		inputCode: 'code04',
		inputTitle: 'ラジオボタン',
		inputLabel: 'ラジオボタンのサブラベルがはいります',
		inputLimit: 300,
		inputContent: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 5,
		inputType: 'headline',
		inputCode: 'code04',
		inputTitle: '見出し',
		inputLabel: '見出しのサブラベルがはいります',
		inputLimit: 300,
		inputContent: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 6,
		inputType: 'paragraph',
		inputCode: 'code04',
		inputTitle:
			'この文章はダミーです。文字の大きさ、量、字間、行間等を確認するために入れています。この文章はダミーです。文字の大きさ、量、字間、行間等を確認するために入れています。この文章はダミーです。文字の大きさ、量、字間、行間等を確認するために入れています。この文章はダミーです。文字の大きさ、量、字間、行間等を確認するために入れています。この文章はダミーです。文字の大きさ、量、字間、行間等を確認するために入れています。この文章はダミーです。文字の大きさ、量、字間、行間等を確認するために入れています。',
		inputLabel: '段落のサブラベルがはいります',
		inputLimit: 300,
		inputContent: '',
		isChecked: false,
		isOpen: false,
	},
	{
		id: 7,
		inputType: 'hr',
		inputCode: 'code04',
		inputTitle: '罫線',
		inputLabel: '罫線のサブラベルがはいります',
		inputLimit: 300,
		inputContent: '',
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

// 初期値を適切なオプションに合わせて設定
const selectedFieldType = ref('text');

//フィールドを追加
const addField = () => {
	// 既存フィールドの最大IDを計算
	const maxId = inputFields.value.length > 0 ? Math.max(...inputFields.value.map((field) => field.id)) : -1;

	const newId = maxId + 1;
	const newField = {
		id: newId,
		inputType: selectedFieldType.value,
		inputCode: `code${String(newId).padStart(2, '0')}`,
		inputTitle: `タイトル${newId + 1}`,
		inputLabel: `タイトルのサブラベルがはいります${newId + 1}`,
		inputLimit: 100, // デフォルトのリミットを設定
		inputContent: '',
		isChecked: false,
		isOpen: false,
	};

	inputFields.value.push(newField);
};

// フィールドを削除する関数
const deleteField = (id) => {
	// idに基づいてフィールドを検索し、そのインデックスを取得
	const index = inputFields.value.findIndex((field) => field.id === id);

	if (index !== -1) {
		// インデックスが見つかった場合、フィールドを削除
		inputFields.value.splice(index, 1);
	} else {
		console.error(`フィールドが見つかりませんでした: id=${id}`);
	}
	// 削除後の処理を行う場合はここに追加
};
</script>

<template>
	<!-- wrap -->
	<div class="max-w-7xl mx-auto px-8">
		<!-- top -->
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

		<!-- content -->
		<div class="max-w-7xl mx-auto flex flex-row bg-white border border-gray-300 rounded-lg overflow-hidden mb-14">
			<!-- セット項目 -->
			<div class="flex-shrink-0 bg-white w-80 border-r border-gray-300">
				<!-- title -->
				<div class="text-gray-500 p-4 border-b border-gray-300 bg-white">
					<h3 class="font-bold text-xl">セット項目</h3>
				</div>

				<!-- select field -->
				<div class="p-4 border-b border-gray-300 bg-white">
					<select v-model="selectedFieldType" class="border rounded py-1 px-2 w-full mb-2" name="" id="">
						<option value="text">テキスト（1行）</option>
						<option value="textarea">テキストエリア（標準）</option>
						<option value="textarea_rtf">テキストエリア（RTF）</option>
						<option value="checkbox">チェックリスト</option>
						<option value="radio">ラジオボタン</option>
						<option value="headline">見出し</option>
						<option value="paragraph">段落</option>
						<option value="hr">罫線</option>
					</select>
					<div class="flex justify-end gap-3">
						<button @click="toggleAll" type="button" class="text-xs text-gray-500">すべて開く / すべて閉じる</button>
						<button @click="addField" class="rounded py-1 px-2 text-xs bg-gray-700 text-white" type="button">フィールドを追加</button>
					</div>
				</div>

				<!-- input field -->
				<ul>
					<li v-for="inputField in inputFields" :key="inputField.id" class="w-full border-b border-gray-300">
						<div class="flex flex-row justify-between items-center p-4 bg-white">
							<!-- input field title -->
							<div>
								<p @click="inputField.isOpen = !inputField.isOpen" v-if="inputField.inputType === 'text'" class="font-bold cursor-pointer">テキスト（1行）</p>
								<p @click="inputField.isOpen = !inputField.isOpen" v-if="inputField.inputType === 'textarea'" class="font-bold cursor-pointer">テキストエリア（標準）</p>
								<p @click="inputField.isOpen = !inputField.isOpen" v-if="inputField.inputType === 'textarea_rtf'" class="font-bold cursor-pointer">テキストエリア（RTF）</p>
								<p @click="inputField.isOpen = !inputField.isOpen" v-if="inputField.inputType === 'checkbox'" class="font-bold cursor-pointer">チェックリスト</p>
								<p @click="inputField.isOpen = !inputField.isOpen" v-if="inputField.inputType === 'radio'" class="font-bold cursor-pointer">ラジオボタン</p>
								<p @click="inputField.isOpen = !inputField.isOpen" v-if="inputField.inputType === 'headline'" class="font-bold cursor-pointer">見出し</p>
								<p @click="inputField.isOpen = !inputField.isOpen" v-if="inputField.inputType === 'paragraph'" class="font-bold cursor-pointer">段落</p>
								<p v-if="inputField.inputType === 'hr'" class="font-bold">罫線</p>
							</div>

							<!-- controller -->
							<div class="ml-auto flex gap-2 items-center">
								<button type="button" class="text-sm"><i class="at-arrow-up-circle"></i></button>
								<button type="button" class="text-sm"><i class="at-arrow-down-circle"></i></button>
								<button @click="deleteField(inputField.id)" type="button" class="text-red-500 text-sm">削除</button>
								<button v-if="!(inputField.inputType === 'hr')" @click="inputField.isOpen = !inputField.isOpen" type="button" class="text-gray-500 text-sm">
									{{ inputField.isOpen ? '閉じる' : '開く' }}
								</button>
							</div>
						</div>

						<!-- detail -->
						<Transition>
							<div v-if="inputField.isOpen" id="detail" class="pl-4 pr-4">
								<!-- title -->
								<div class="mb-2">
									<p class="text-xs text-gray-500 mb-1">タイトル</p>
									<input v-model="inputField.inputTitle" class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" placeholder="タイトル" />
								</div>
								<!-- sub label -->
								<div v-if="!(inputField.inputType === 'hr')" class="mb-2">
									<p class="text-xs text-gray-500 mb-1">サブラベル</p>
									<input v-model="inputField.inputLabel" class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="サブラベルが入ります" />
								</div>

								<!-- checkbox -->
								<div v-if="inputField.inputType === 'checkbox'" class="mb-2">
									<p class="text-xs text-gray-500 mb-1">チェックリスト（1行で1つ）</p>
									<textarea class="w-full border rounded border-gray-300" name="" id="" cols="10"></textarea>
								</div>

								<!-- radio -->
								<div v-if="inputField.inputType === 'radio'" class="mb-2">
									<p class="text-xs text-gray-500 mb-1">ラジオボタン（1行で1つ）</p>
									<textarea class="w-full border rounded border-gray-300" name="" id="" cols="10"></textarea>
								</div>

								<div v-if="!(inputField.inputType === 'hr')" class="flex gap-4 pb-4">
									<!-- limit -->
									<div
										v-if="
											!(
												inputField.inputType === 'checkbox' ||
												inputField.inputType === 'radio' ||
												inputField.inputType === 'headline' ||
												inputField.inputType === 'paragraph' ||
												inputField.inputType === 'hr'
											)
										"
										class="mb-2">
										<p class="text-xs text-gray-500 mb-1">文字数制限</p>
										<input v-model="inputField.inputLimit" class="border border-gray-300 rounded w-24 py-1 px-2 text-sm" type="number" placeholder="100" />
									</div>

									<!-- required -->
									<div v-if="!(inputField.inputType === 'paragraph' || inputField.inputType === 'headline' || inputField.inputType === 'hr')" class="mb-2">
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
				<!-- title -->
				<div class="text-gray-500 p-4 border-b border-gray-300 bg-white"><h3 class="font-bold text-xl">プレビュー</h3></div>

				<!-- list -->
				<div class="max-w-4xl mx-auto p-8">
					<ul>
						<li v-for="inputField in inputFields" :key="inputField.id" class="mb-8">
							<div class="flex gap-2 items-center">
								<!-- title -->
								<h4 v-if="!(inputField.inputType === 'headline' || inputField.inputType === 'paragraph' || inputField.inputType === 'hr')" class="font-bold text-lg">
									{{ inputField.inputTitle }}
								</h4>

								<!-- required -->
								<p v-if="inputField.isChecked" class="bg-red-500 text-white text-xs inline-flex items-center justify-center py-0.5 px-2 rounded-full">必須</p>
							</div>

							<!-- headline -->
							<h1 v-if="inputField.inputType === 'headline'" class="text-xl font-bold mb-2">{{ inputField.inputTitle }}</h1>

							<!-- paragraph -->
							<p v-if="inputField.inputType === 'paragraph'" class="mb-2">{{ inputField.inputTitle }}</p>

							<div class="flex justify-between mb-2">
								<!-- label -->
								<div v-if="!(inputField.inputType === 'hr')">
									<p class="text-sm text-gray-400">{{ inputField.inputLabel }}</p>
								</div>
								<!-- limit -->
								<div v-if="inputField.inputType === 'text' || inputField.inputType === 'textarea' || inputField.inputType === 'textarea_rtf'">
									<p class="text-sm text-gray-900">{{ inputField.inputContent.length }} / {{ inputField.inputLimit }}文字</p>
								</div>
							</div>

							<!-- input type -->
							<div>
								<!-- input -->
								<input v-if="inputField.inputType === 'text'" v-model="inputField.inputContent" class="w-full border rounded border-gray-300 p-2 mb-1" type="text" value="" />

								<!-- textare -->
								<textarea v-if="inputField.inputType === 'textarea'" type="textarea" v-model="inputField.inputContent" class="w-full border rounded border-gray-300 p-2 h-32"></textarea>

								<!-- textare_rtf -->
								<!-- tiny MCEへ置き換える -->
								<textarea v-if="inputField.inputType === 'textarea_rtf'" type="textarea" v-model="inputField.inputContent" class="w-full border rounded border-gray-300 p-2 h-32"></textarea>

								<!-- checkbox -->
								<div v-if="inputField.inputType === 'checkbox'">
									<input type="checkbox" />
									<label for="checkbox">ラベル</label>
								</div>

								<!-- radio -->
								<div v-if="inputField.inputType === 'radio'">
									<input type="radio" />
									<label for="radio">ラベル</label>
								</div>

								<!-- hr -->
								<hr v-if="inputField.inputType === 'hr'" class="my-8 border-gray-400" />
							</div>

							<!-- code -->
							<div v-if="!(inputField.inputType === 'headline' || inputField.inputType === 'paragraph' || inputField.inputType === 'hr')" class="flex justify-end text-xs text-gray-400">
								<p v-text="inputField.inputCode"></p>
							</div>
						</li>
					</ul>

					<!-- <hr class="my-8 border-gray-300" /> -->
				</div>
			</div>

			<div class="w-1/2 p-4" style="font-size: 10px">
				<p style="white-space: pre-wrap">
					{{ inputFields }}
				</p>
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

li:last-child {
	border: none;
}
</style>
