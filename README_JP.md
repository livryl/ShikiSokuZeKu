# Shiki Soku Ze Ku (色即是空)

[English](README.md) | 日本語

ComfyUIを簡単に扱うための統合UIです。

### ダウンロードはこちら(Zipです) → https://github.com/livryl/ShikiSokuZeKu/releases/tag/v1.02

ページ下の **Assets** にある zip をダウンロードしてください(「Source code」ではありません)。

## 主な機能

- 画像生成 (T2I)
- 画像編集 (I2I)
- PNGInfo読込
- モデル一覧(サムネ付き)
- LoRA管理
- タグ予測変換(データは同梱していません。下の「タグ予測変換のデータ」を参照)
- プロンプト拡張(日本語→英語の翻訳にも使えます・任意)
- 動画生成 (MiniMax H3・参照画像/音声・シーン分割での長尺対応)
- 音声生成 (Irodori-TTS・リファレンス音声・スタイル指定・絵文字パレット)
- 音楽生成 (Stable Audio 3)

## 必要なもの

1. Windows
2. ComfyUI(先に起動しておく)
   - 標準のURL: http://127.0.0.1:8188
   - StabilityMatrix 版でも、通常の ComfyUI でも使えます
3. Python 3.10 以上
   - start.bat が見つけます。無い場合は python.org から入れてください
   - インストーラーで「Add python.exe to PATH」にチェックを入れてください
4. 使いたい機能ごとのモデル・ノード(下の「機能ごとに必要なもの」を見てください)

※ 生成の重さはモデルしだいです。作者の環境は RTX 3060 12GB です。

## 初回セットアップ

1. ComfyUI を起動する
2. start.bat をダブルクリック
   - 初回だけ、専用の環境(Data\venv)を作って gradio などを入れます。数分かかります
   - 終わるとブラウザが自動で開きます
3. 画面右上の ⚙ 設定 を開いて、必要なら次を設定して「保存して閉じる」
   - 一般 > ComfyUIのURL(標準のままなら変更不要)
   - フォルダ > モデル / LoRA のフォルダ(任意)
     - 空欄でも動きます(ComfyUI が見えているモデル一覧を使います)
     - 指定するとサムネイルが出て、LoRA・モデルの絞り込みもできます
     - ※ ComfyUI 側でも同じフォルダを読む設定にしてください
4. T2I タブでモデルを選んで「生成する」

2回目以降は、start.bat を実行するか、自動でできる「Shiki Soku Ze Ku.lnk」を使います。
起動中にもう一度起動すると、いまのUIを開き直すだけです。
終了は、画面右上の「⏻ 終了」ボタンです。

使い方や各項目の説明は、起動後のヘッダー右の「📘」ボタンから読めます。

## 機能ごとに必要なもの

(使わない機能のものは不要です。モデル名は標準値で、設定から変更できます)

### 画像 T2I / I2I

- Anima: Anima のモデル(diffusion_models)と、必要なら Turbo LoRA
- ほかのタイプ(SDXL / Krea2 / Flux2 Klein / Z-Image):
  - モデル本体のほかに、CLIP と VAE が必要です
  - 初回起動時に Data\workflow_krea2.json などが自動で作られるので、その中のファイル名を自分の環境に合わせて書き換えてください
- Anima 以外のタイプは、作者の環境で未検証の部分があります

### 動画 (MiniMax H3 の参照動画生成)

- ComfyUI 本体が MiniMax H3 に対応した版であること
- models に次の4つ(名前は標準値)
  - diffusion_models: `minimax_h3_ref2va_pruned_int8_convrot.safetensors`
  - text_encoders: `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`
  - vae: `minimax_h3_video_vae_fp16.safetensors`
  - vae: `minimax_h3_audio_vae_fp32.safetensors`
- Turbo を使うなら Turbo LoRA(`minimax_h3_ref2v_turbo_...safetensors`)
- SageAttention を使うなら KJNodes(任意)

### 音楽 (Stable Audio 3 Medium)

- checkpoints: `stable_audio_3_medium.safetensors`
- text_encoders:
  - `t5gemma_b_b_ul2.safetensors`
  - `qwen3.5_2b_bf16.safetensors`(プロンプト拡張を使う時だけ)
- 入手先: HuggingFace の Comfy-Org/stable-audio-3 と Comfy-Org/Qwen3.5
- workflow_audio.json は ComfyUI のテンプレートを「API形式」で書き出したものです

### 音声 (Irodori-TTS)

- ComfyUI のカスタムノード: jupo-ai/comfy_IrodoriTTS
- checkpoints: Irodori-TTS のモデル(例: `Irodori-TTS-v4.1-Small.safetensors`)
- 導入後に ComfyUI を再起動してください
- 新しいバージョンのモデルでは、ノード側の修正が必要な場合があります
- custom_nodes の中に、ノードのバックアップコピーを置かないでください(二重読み込みになります)

## タグ予測変換のデータ(任意・同梱していません)

プロンプト入力中に出るタグ予測変換(danbooruタグ+日本語訳)は、外部で配布されているCSVを使います。
配布元のものなので、このUIには付属していません。使いたい人は、下のページから各自ダウンロードしてください。

入手先: https://civitai.com/models/2018479/danbooru-tag-complete-csv-tagcompleteand

1. 上のページから zip をダウンロードして、解凍する
2. 中の2つのファイルを Data\ フォルダの直下に置き、名前を次のように変更する
   - `danbooru_日付.csv` → `danbooru.csv`(必須。これが無いと予測変換は動きません)
   - `danbooru_translations_jp.csv` → `danbooru-jp.csv`(日本語訳。無くても動きますが、日本語で検索できません)
   - ※ 日付の部分はバージョンで変わります(例: danbooru_20250919.csv)
3. UI を起動(起動中なら「保存して再起動」)
   - 初回だけ tags.json が自動で作られます。少し時間がかかります
4. 使わない時は、⚙設定 > 一般 > 「タグ予測変換を使う」をOFFにできます

※ 無くても、ほかの機能は普通に動きます(予測変換が出ないだけです)
※ CSVの利用条件は、配布ページで確認してください

## ファイルの自動整理(任意・初期はOFF)

⚙設定 > フォルダ の「ComfyUI側のファイル整理」をONにすると、次のファイルを自動で削除します。

- コピー後に ComfyUI の output に残ったファイル
- このUIが ComfyUI の input に置いた画像・音声

ONにする時は、ComfyUI の output / input フォルダを指定してください。
削除するのは、指定フォルダの中の「このUIが作ったファイル」だけです。

## 困った時

- 「ComfyUIに接続できません」
  - ComfyUI が起動しているか、⚙設定のURLが合っているか確認してください
- 画面が開かない / すぐ終わる
  - Data\anima_ui.log を見てください。起動に失敗した時はメッセージも出ます
- 動画・音楽・音声のタブが出ない
  - 対応する *_core.py が Data にあるか確認してください。無いタブは出ない仕様です
  - ある場合は anima_ui.log に理由が出ます
- モデルが一覧に出ない
  - ComfyUI 側で見えているか確認 → モデル横の 🔄 で再読込
- 「ComfyUIから見えないモデル」の警告
  - ⚙で指定したフォルダを、ComfyUI 側でも読むようにしてください(extra_model_paths.yaml など)
- 通信は自分のPC内(127.0.0.1)だけです。外部には公開されません

## ライセンス・注意

このソフトは無償配布です。

ComfyUIおよび各種モデル・カスタムノードを利用して動作します。
各モデル・カスタムノードのライセンスは、それぞれの配布元の規約に従ってください。

作者は個人利用環境で動作確認していますが、
すべての環境での動作は保証しません。

## 制作

2026 えーてぃーえふ Livryl
https://x.com/ATFzwei
