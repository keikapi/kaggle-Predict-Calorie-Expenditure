# kaggle-Predict-Calorie-Expenditure

## 1. コンペ進め方（ステップバイステップ）

① コンペ内容の理解

データ概要・評価指標（MAE）を理解。基本は回帰タスク。

② 環境準備

SageMaker StudioでNotebook環境を用意し、S3とGitHubを接続。

③ EDA（探索的データ分析）

各特徴量の分布・相関・欠損値チェック。仮説を立てる。

④ 前処理

スケーリング、欠損補完、カテゴリ変数エンコードなど。

⑤ モデリング

XGBoost / LightGBM / RandomForest / NNなどから試す。

⑥ 評価・CV設計

KFoldやStratifiedKFoldで交差検証し、CVとLBの差を把握。

⑦ アンサンブル

複数モデルの平均・スタッキングで性能向上を狙う。

⑧ 提出と分析

Submit後、スコア・フィードバックを基に改善を繰り返す。



## 2. データ管理

本プロジェクトの各種データをGitHub + S3 を利用して、以下の構成
で管理します。

### ・GitHub（コード・設定ファイル管理）

kaggle-Predict-Calorie-Expenditure/

data/  　軽量サンプルデータ or metadata（.gitignore推奨）

notebooks/   　分析用Notebook（EDA, Model, Ensemble）

scripts/    　モデル構築・学習・推論用スクリプト（.py）

config/       　ハイパーパラメータや環境設定（YAML/JSON）

outputs/      　ローカル検証用submitファイル、予測結果（.gitignore）

requirements.txt     　依存ライブラリ

README.md       　プロジェクト概要



### ・S3（中間生成物・成果物ストレージ）

s3://datascience-keigo/kaggle-Predict Calorie Expenditure/

raw/  　元データ（train.csv, test.csv）

processed/         　前処理後データ（train_proc.pklなど）

models/            　学習済モデル（.pkl, .joblib）

submissions/      　提出ファイル（.csv）

logs/        　学習ログ・評価結果

auth/　認証情報

## 3. メタデータ管理

AWS Glue Data Catalogを利用して、メタデータ管理を実施します。

## 4. ChatGPTチャットリンク

https://chatgpt.com/share/6820917f-d2e0-800c-968b-cf54c4bf7f3e
 