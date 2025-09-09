> このリポジトリは [Isaac Sim 公式リポジトリ](https://github.com/isaac-sim/IsaacSim) をフォークしたものです。最新情報については元のリポジトリをご参照ください。

> 詳細は `./README_original.md` をご覧ください。

# Isaac Sim

NVIDIA Isaac Sim™は、NVIDIA Omniverse上に構築されたロボットシミュレーションプラットフォームです。URDFやMJCF、CADなどの一般的なロボットフォーマットのインポートに対応し、高精度なGPUアクセラレート物理エンジンによるリアルな動作や複数センサーのRTXレンダリングを実現します。合成データ生成、強化学習、ROS連携、デジタルツインなど、ロボット開発の各段階を支援するワークフローを提供します。

### 必要なソフトウェア依存関係

- [**Git**](https://git-scm.com/downloads): バージョン管理用
- [**Git LFS**](https://git-lfs.com/): 大容量ファイル管理用
- **(Windows - C++のみ) Visual Studio 2019/2022**: C++デスクトップ開発ワークロードを選択
- **(Windows - C++のみ) Windows SDK**: Visual Studio Installerで追加
- **(Linux) build-essential**: 必要なビルドツール。Ubuntuは以下でインストール:
  ```bash
  sudo apt-get install build-essential
  ```

  > **(Linux) ⚠️**
  > GCC/G++ 11 を使用してください。より高いバージョンはまだサポートされていません。GCC/G++ 11 のインストールは以下のコマンドを実行してください:
  > ```bash
  > sudo apt-get install gcc-11 g++-11
  > sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-11 200
  > sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-11 200
  > ```

## クイックスタート

このセクションではIsaac Simをソースコードからビルドする手順を説明します。

### 1. リポジトリのクローン


```bash
git clone https://github.com/ss-khor/isaac-sim.git
cd isaac-sim
git lfs install
git lfs pull
```

### 2. ビルド

設定ウィザードを開始するには以下のコマンドを実行してください:

**Linux:**

ビルド前にGCC/G++ 11が使用されていることを確認してください:

```bash
gcc --version
g++ --version
```

```bash
./build.sh
```

**Windows:**

> **⚠️ Windowsのパス長制限**
> Windowsには260文字のパス長制限があります。ファイルが見つからない等のエラーが発生した場合は、リポジトリをより短いパスに移動してください。

```powershell
build.bat
```

### 3. 実行

> **⚠️ 起動時間について**
> 初回のIsaac Sim起動時は、拡張機能やシェーダーのロード・キャッシュに数分かかる場合があります。2回目以降はハードウェア構成にもよりますが10～30秒程度です。



プラットフォームに応じたバイナリディレクトリに移動し、実行ファイルを起動してください。

**Linux:**
```bash
cd _build/linux-x86_64/release
./isaac-sim.sh
```

**Windows:**
```powershell
cd _build/windows-x86_64/release
isaac-sim.bat
```

> 注: 初回ビルド時にはOmniverseライセンス規約への同意が求められます。