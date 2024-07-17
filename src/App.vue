<script setup>
import {ref} from 'vue';
const field = ref('');
</script>
<template>
	<div class="max-w-7xl mx-auto px-8">
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

		<div class="max-w-7xl mx-auto flex flex-row bg-white border border-gray-300 rounded-lg overflow-hidden">
			<!-- セット項目 -->
			<!-- row -->
			<div class="flex-shrink-0 bg-white w-80 border-r border-gray-300">
				<div class="text-gray-500 p-4 border-b border-gray-300">
					<h3 class="font-bold text-xl">セット項目</h3>
				</div>

				<!-- セレクタ -->
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
					<div class="flex justify-end">
						<button class="rounded py-1 px-2 text-xs bg-gray-700 text-white" type="button">フィールドを追加</button>
					</div>
				</div>
				<ul>
					<!-- list -->
					<li class="w-full border-b border-gray-300">
						<!-- show -->
						<div class="flex flex-row justify-between items-center p-4">
							<p class="font-bold">テキスト</p>
							<!-- コントローラー -->
							<div class="ml-auto flex gap-4 items-center">
								<buttoni id="up" type="button" class="text-sm"><i class="at-arrow-up-circle"></i></buttoni>
								<buttoni id="down" type="button" class="text-sm"><i class="at-arrow-down-circle"></i></buttoni>
								<buttoni id="delete" type="button" class="text-red-500 text-sm">削除</buttoni>
								<buttoni id="open" type="button" class="text-gray-400 text-sm">開く</buttoni>
							</div>
						</div>

						<!-- detail -->
						<div class="pl-4 pr-4 pb-4">
							<div class="mb-2">
								<p class="text-xs text-gray-500 mb-1">コード</p>
								<input class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="コード" />
							</div>
							<div class="mb-2">
								<p class="text-xs text-gray-500 mb-1">タイトル</p>
								<input v-model="field" class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="タイトル" />
							</div>
							<div class="mb-2">
								<p class="text-xs text-gray-500 mb-1">サブラベル</p>
								<input class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="サブラベルが入ります" />
							</div>
							<div class="flex gap-4">
								<div class="mb-2">
									<p class="text-xs text-gray-500 mb-1">文字数制限</p>
									<input class="border border-gray-300 rounded w-24 py-1 px-2 text-sm" type="text" value="" placeholder="100" />
								</div>
								<div class="mb-2">
									<p class="text-xs text-gray-500 mb-1">必須</p>
									<input class="w-4 h-4 border-gray-400 rounded" type="checkbox" name="required" id="" value="必須" checked />
								</div>
							</div>
						</div>
					</li>
				</ul>
			</div>

			<!-- プレビュー -->
			<div class="w-full mx-auto flex-initial bg-white">
				<div class="text-gray-500 p-4 border-b border-gray-300"><h3 class="font-bold text-xl">プレビュー</h3></div>

				<div class="max-w-4xl mx-auto p-8">
					<!-- card -->
					<div class="mb-8">
						<div class="flex gap-2 items-center">
							<h4 class="font-bold text-lg">タイトル</h4>
							<p class="bg-red-500 text-white text-xs inline-flex items-center justify-center py-0.5 px-2 rounded-full">必須</p>
						</div>
						<div class="flex justify-between mb-2">
							<p class="text-sm text-gray-400">タイトルのサブラベルが入ります</p>
							<p class="text-sm text-gray-900">0 / 100 文字</p>
						</div>
						<!--  -->
						<!--  -->
						<!--  -->
						<!--  -->
						<!--  -->
						<!--  -->
						<input class="w-full border rounded border-gray-300 p-2" type="text" value="" />
					</div>

					<!-- card -->
					<div class="mb-8">
						<div class="flex gap-2 items-center">
							<h4 class="font-bold text-lg">所属機関名</h4>
							<p class="bg-red-500 text-white text-xs inline-flex items-center justify-center py-0.5 px-2 rounded-full">必須</p>
						</div>
						<div class="flex justify-between mb-2">
							<p class="text-sm text-gray-400">所属機関名のサブラベルが入ります</p>
							<p class="text-sm text-gray-900">0 / 600 文字</p>
						</div>
						<textarea class="w-full border rounded border-gray-300 p-2 h-32" type="text" value="" />
					</div>

					<!-- card -->
					<div class="mb-8">
						<div class="flex gap-2 items-center">
							<h4 class="font-bold text-lg">所属</h4>
						</div>
						<div class="flex justify-between mb-2">
							<p class="text-sm text-gray-400">所属機関名のサブラベルが入ります</p>
							<!-- <p class="text-sm text-gray-900">0 / 600 文字</p> -->
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
					</div>

					<!-- card -->
					<div class="mb-8">
						<div class="flex gap-2 items-center">
							<h4 class="font-bold text-lg">カテゴリー</h4>
						</div>
						<div class="flex justify-between mb-2">
							<p class="text-sm text-gray-400">カテゴリーのサブラベルが入ります</p>
							<!-- <p class="text-sm text-gray-900">0 / 600 文字</p> -->
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
					</div>

					<hr class="my-8 border-gray-300" />
				</div>
			</div>
		</div>
	</div>
	<div class="fixed bottom-0 w-full border-t border-gray-300 bg-white">
		<div class="max-w-7xl mx-auto flex justify-end py-4 px-8">
			<button type="button" class="rounded text-md text-white bg-gray-700 font-bold px-4 py-1">更新する</button>
		</div>
	</div>
</template>
