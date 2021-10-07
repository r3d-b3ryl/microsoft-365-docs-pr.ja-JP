---
title: 自動化フォルダーの除外を管理する
description: 自動化フォルダーの除外を追加して、自動調査から除外されるファイルを制御します。
keywords: 管理, 自動化, 除外, ブロック, クリーン, 悪意のある
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 09bd7b0318169e69e91a511c9d27033c5aeb0efa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151980"
---
# <a name="manage-automation-folder-exclusions"></a>自動化フォルダーの除外を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

オートメーション フォルダーの除外を使用すると、自動調査がスキップするフォルダーを指定できます。

スキップするフォルダーに関する次の属性を制御できます。

- **フォルダー**: スキップするフォルダーとそのサブフォルダーを指定できます。

  > [!NOTE]
  > 現時点では、ディレクトリ内のファイルを除外する方法としてワイルドカードを使用する方法はまだサポートされていません。

- **ファイルの拡張子**: 特定のディレクトリで除外する拡張子を指定できます。 拡張機能は、攻撃者が除外フォルダーを使用して悪用を隠すのを防ぐ方法です。 拡張機能は、無視するファイルを明示的に定義します。

- **ファイル名**: 特定のディレクトリで除外するファイル名を指定できます。 名前は、攻撃者が除外されたフォルダーを使用して悪用を隠すのを防ぐ方法です。 名前は、無視するファイルを明示的に定義します。

## <a name="add-an-automation-folder-exclusion"></a>オートメーション フォルダーの除外を追加する

1. ナビゲーション ウィンドウで、[エンドポイント **ルールの設定** \> **除外**] \>  \> **を選択します**。

2. [新 **しいフォルダーの除外] をクリックします**。

3. フォルダーの詳細を入力します。

    - フォルダー
    - 拡張機能
    - ファイル名
    - 説明

4. **[保存]** をクリックします。

> [!NOTE]
> 除外されたファイルを収集または調べる Live Response コマンドは、"ファイルが除外されました" というエラーで失敗します。 さらに、自動調査では除外されたアイテムは無視されます。

## <a name="edit-an-automation-folder-exclusion"></a>オートメーション フォルダーの除外を編集する

1. ナビゲーション ウィンドウで、[エンドポイント **ルールの設定** \> **除外**] \>  \> **を選択します**。
2. フォルダーの **除外で** [編集] をクリックします。
3. ルールの詳細を更新し、[保存] を **クリックします**。

## <a name="remove-an-automation-folder-exclusion"></a>オートメーション フォルダーの除外を削除する

1. ナビゲーション ウィンドウで、[エンドポイント **ルールの設定** \> **除外**] \>  \> **を選択します**。
2. [除外 **の削除] をクリックします**。

## <a name="related-topics"></a>関連トピック

- [許可/ブロックされたリストの自動化を管理する](manage-indicators.md)
- [自動化ファイルのアップロードを管理する](manage-automation-file-uploads.md)
