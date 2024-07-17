<script setup></script>

<template>
	<div className="max-w-7xl mx-auto px-8">
		<div className="mt-8 mb-4">
			<div className="flex gap-4 border-b border-gray-300 pb-2">
				<p className="text-lg text-gray-900 font-bold">入力項目編集画面</p>
				<div className="ml-auto">
					<a href="#">フォームに戻る</a>
				</div>
			</div>
			<!-- プロジェクト・フォーム -->
			<div className="flex gap-4 pt-2">
				<div className="flex flex-row items-center">
					<p className="text-sm text-gray-400">プロジェクト名：</p>
					<h2 className="text-sm text-gray-900 font-bold">全国肢体不自由児学会</h2>
				</div>
				<div className="flex flex-row items-center">
					<p className="text-sm text-gray-400">フォーム名：</p>
					<h2 className="text-sm text-gray-900 font-bold">演題登録</h2>
				</div>
			</div>
		</div>

		<div className="max-w-7xl mx-auto flex flex-row bg-white border border-gray-300 rounded-lg overflow-hidden">
			<!-- セット項目 -->
			<!-- row -->
			<div className="flex-shrink-0 bg-white w-80 border-r border-gray-300">
				<div className="text-gray-500 p-4 border-b border-gray-300">
					<h3 className="font-bold text-xl">セット項目</h3>
				</div>

				<!-- セレクタ -->
				<div className="p-4 border-b border-gray-300">
					<select className="border rounded py-1 px-2 w-full mb-2" name="" id="">
						<option value="#">テキスト（1行）</option>
						<option value="#">テキストエリア（プレーン）</option>
						<option value="#">テキストエリア（リッチテキスト）</option>
						<option value="#">チェックリスト</option>
						<option value="#">ラジオボタン</option>
						<option value="#">見出し</option>
						<option value="#">段落</option>
						<option value="#">罫線</option>
					</select>
					<div className="flex justify-end">
						<button className="rounded py-1 px-2 text-xs bg-gray-700 text-white" type="button">フィールドを追加</button>
					</div>
				</div>
				<!-- card テキスト -->
				<div className="w-full p-5 border-b border-gray-300">
					<!-- タイトル -->
					<div className="flex flex-row justify-between items-center">
						<p className="font-bold">テキスト</p>
						<button type="button" className="text-red-500 text-xs">削除</button>
					</div>

					<!-- オプション -->
					<div className="">
						<div className="mb-2">
							<p className="text-xs text-gray-500 mb-1">名前</p>
							<input className="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="タイトル" />
						</div>
						<div className="mb-2">
							<p className="text-xs text-gray-500 mb-1">サブラベル</p>
							<input className="border border-gray-300 rounded w-full py-1 px-2 text-sm" type="text" value="" placeholder="タイトルのサブラベルが入ります" />
						</div>
						<div className="flex gap-4">
							<div className="mb-2">
								<p className="text-xs text-gray-500 mb-1">文字数制限</p>
								<input className="border border-gray-300 rounded w-24 py-1 px-2 text-sm" type="text" value="" placeholder="100" />
							</div>
							<div className="mb-2">
								<p className="text-xs text-gray-500 mb-1">必須</p>
								<input className="w-4 h-4 border-gray-400 rounded" type="checkbox" name="required" id="" value="必須" checked />
							</div>
						</div>
					</div>
				</div>
			</div>

			<!-- row -->
			<!-- プレビュー -->
			<div className="w-full mx-auto flex-initial bg-white">
				<div className="text-gray-500 p-4 border-b border-gray-300"><h3 className="font-bold text-xl">プレビュー</h3></div>

				<div className="max-w-4xl mx-auto p-8">
					<!-- card -->
					<div className="mb-8">
						<div className="flex gap-2 items-center">
							<h4 className="font-bold text-lg">タイトル</h4>
							<p className="bg-red-500 text-white text-xs inline-flex items-center justify-center py-0.5 px-2 rounded-full">必須</p>
						</div>
						<div className="flex justify-between mb-2">
							<p className="text-sm text-gray-400">タイトルのサブラベルが入ります</p>
							<p className="text-sm text-gray-900">0 / 100 文字</p>
						</div>
						<input className="w-full border rounded border-gray-300 p-2" type="text" value="" />
					</div>

					<!-- card -->
					<div className="mb-8">
						<div className="flex gap-2 items-center">
							<h4 className="font-bold text-lg">所属機関名</h4>
							<p className="bg-red-500 text-white text-xs inline-flex items-center justify-center py-0.5 px-2 rounded-full">必須</p>
						</div>
						<div className="flex justify-between mb-2">
							<p className="text-sm text-gray-400">所属機関名のサブラベルが入ります</p>
							<p className="text-sm text-gray-900">0 / 600 文字</p>
						</div>
						<textarea className="w-full border rounded border-gray-300 p-2 h-32" type="text" value="" />
					</div>

					<!-- card -->
					<div className="mb-8">
						<div className="flex gap-2 items-center">
							<h4 className="font-bold text-lg">所属</h4>
						</div>
						<div className="flex justify-between mb-2">
							<p className="text-sm text-gray-400">所属機関名のサブラベルが入ります</p>
							<!-- <p className="text-sm text-gray-900">0 / 600 文字</p> -->
						</div>
						<div className="flex gap-5">
							<div className="flex gap-2">
								<input type="checkbox" name="" id="" />
								<label for="">医者</label>
							</div>
							<div className="flex gap-2">
								<input type="checkbox" name="" id="" />
								<label for="">研修医</label>
							</div>
							<div className="flex gap-2">
								<input type="checkbox" name="" id="" />
								<label for="">看護師</label>
							</div>
						</div>
					</div>

					<!-- card -->
					<div className="mb-8">
						<div className="flex gap-2 items-center">
							<h4 className="font-bold text-lg">カテゴリー</h4>
						</div>
						<div className="flex justify-between mb-2">
							<p className="text-sm text-gray-400">カテゴリーのサブラベルが入ります</p>
							<!-- <p className="text-sm text-gray-900">0 / 600 文字</p> -->
						</div>
						<div className="flex gap-5">
							<div className="flex gap-2">
								<input type="radio" name="radio" id="" />
								<label for="">コメディカル</label>
							</div>
							<div className="flex gap-2">
								<input type="radio" name="radio" id="" />
								<label for="">なんとかかんとか</label>
							</div>
							<div className="flex gap-2">
								<input type="radio" name="radio" id="" />
								<label for="">ああだこうだ</label>
							</div>
						</div>
					</div>

					<hr className="my-8 border-gray-300" />
				</div>
			</div>
		</div>
	</div>
	<div className="fixed bottom-0 w-full border-t border-gray-300 bg-white">
		<div className="max-w-7xl mx-auto flex justify-end py-4">
			<button type="button" className="rounded text-md text-white bg-gray-700 font-bold px-4 py-1">更新する</button>
		</div>
	</div>
</template>
