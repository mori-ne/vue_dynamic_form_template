<script setup></script>

<template>
	<div class="p-6 max-w-8xl mx-auto">
		<!-- プロジェクト・フォーム -->
		<div class="mb-6">
			<div class="flex flex-row items-center">
				<p class="text-sm text-gray-400">プロジェクト名：</p>
				<h2 class="text-md text-gray-900 font-bold">全国肢体不自由児学会</h2>
			</div>
			<div class="flex flex-row items-center">
				<p class="text-sm text-gray-400">フォーム名：</p>
				<h2 class="text-md text-gray-900 font-bold">演題登録</h2>
			</div>
		</div>

		<div class="flex flex-row bg-white border border-gray-300 rounded-lg overflow-hidden">
			<!-- row -->
			<div class="flex-shrink-0 bg-white w-80 border-r border-gray-300">
				<div class="bg-gray-500 text-white p-4 border-b border-gray-300">
					<h3 class="font-bold text-xl">入力項目</h3>
				</div>

				<!-- card テキスト -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">テキスト</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>

					<!-- オプション -->
					<div class="">
						<div class="mb-2">
							<p class="text-xs text-gray-500 mb-1">名前</p>
							<input class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="タイトル" />
						</div>
						<div class="mb-2">
							<p class="text-xs text-gray-500 mb-1">サブラベル</p>
							<input class="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="タイトルのサブラベルが入ります" />
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

					<!-- 開閉 -->
					<div class="flex justify-center text-xs">
						<i class="at-download-arrow-down"></i>
					</div>
				</div>

				<!-- card テキストエリア（プレーン） -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">テキストエリア（プレーンテキスト）</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>
					<!-- 開閉 -->
					<div class="flex justify-center text-xs">
						<i class="at-download-arrow-down"></i>
					</div>
				</div>

				<!-- card テキストエリア（リッチテキスト） -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">テキストエリア（リッチテキスト）</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>
				</div>

				<!-- card ラジオボタン -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">ラジオボタン</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>
				</div>

				<!-- card チェックボタン -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">チェックボタン</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>
				</div>

				<!-- card ドロップダウンメニュー -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">ドロップダウンメニュー</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>
				</div>

				<!-- card 見出し -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">見出し</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>
				</div>

				<!-- card 段落 -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">段落</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>
				</div>

				<!-- card 罫線 -->
				<div class="w-full p-6 border-b border-gray-300">
					<!-- タイトル -->
					<div class="flex flex-row justify-between items-center mb-3">
						<p class="font-bold">罫線</p>
						<button class="py-1 px-4 bg-gray-700 text-white rounded text-xs" type="button">追加</button>
					</div>
				</div>
			</div>

			<!-- row -->
			<!-- プレビュー -->
			<div class="w-full mx-auto flex-initial bg-white">
				<div class="bg-gray-200 text-gray-900 p-4 border-b border-gray-300"><h3 class="font-bold text-xl">プレビュー</h3></div>

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
						<input class="w-full border rounded border-gray-300 p-2" type="text" value="" />
						<div class="flex justify-end">
							<a href="#" class="text-xs text-red-500 mt-1">削除</a>
						</div>
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
						<div class="flex justify-end">
							<a href="#" class="text-xs text-red-500 mt-1">削除</a>
						</div>
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
						<div class="flex gap-6">
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
						<div class="flex justify-end">
							<a href="#" class="text-xs text-red-500 mt-1">削除</a>
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
						<div class="flex gap-6">
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
						<div class="flex justify-end">
							<a href="#" class="text-xs text-red-500 mt-1">削除</a>
						</div>
					</div>

					<hr class="my-8 border-gray-300" />
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped></style>
