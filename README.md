# 機械学習と物理学：計算実習ノートブック

新潟大学理学部 集中講義「物理学特論II：機械学習と物理学」（2026年9月28〜30日、担当 富谷昭夫）の計算実習用ノートブックです。
すべて Google Colab で動きます。手元の環境構築は必要ありません。

| ノートブック | 内容 | 講義ノート | Colab |
|---|---|---|---|
| `01_ising_metropolis_julia.ipynb` | 2次元イジング模型の Metropolis 法、熱化、⟨\|m\|⟩・χ・Binder キュムラントによる T_c の読み取り、配位データの作成とダウンロード | 第2・3章 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/akio-tomiya/niigata2026-ml-physics/blob/main/notebooks/01_ising_metropolis_julia.ipynb) |
| `02_phase_classification_keras.ipynb` | Keras によるロジスティック回帰・全結合ネット・CNN での相分類、P_ord(T) と T*、分類器が何を見ていたかの確認、交差検証 | 第4・5章 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/akio-tomiya/niigata2026-ml-physics/blob/main/notebooks/02_phase_classification_keras.ipynb) |

## 使い方

1. 上の「Open in Colab」から 01 を開き、「ランタイム」→「ランタイムのタイプを変更」で **Julia** を選んで上から順に実行します。
   最後のセルで `ising_L16.npz` ができるので、左の「ファイル」パネルからダウンロードします。
2. 02 を開き（ランタイムは Python 3）、上から順に実行します。
   01 で作ったファイルを使うときは `USE_UPLOAD = True` にしてアップロードします。
   そうでなければ、このリポジトリの `data/ising_L16.npz`（01 と同じコードで作ったもの）を自動で読み込みます。

## データ `data/ising_L16.npz`

- `configs`：配位（形は (5200, 16, 16)、値は ±1）
- `T`：温度（1.0〜3.5、0.1 刻みの26点。J = k_B = 1）
- `chain`：連鎖の番号（各温度で独立な連鎖 0〜3 の4本、1本から50配位）
- `L`：格子の1辺（16）

Metropolis 法、周期境界、熱化2000スイープ、測定間隔10スイープ。T < T_c は全スピン上向き、T > T_c はランダムな配位から開始。

## ライセンス

MIT License
