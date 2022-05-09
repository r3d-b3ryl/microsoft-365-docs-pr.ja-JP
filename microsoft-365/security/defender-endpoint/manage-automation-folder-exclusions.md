---
title: 自動化フォルダーの除外を管理する
description: オートメーション フォルダーの除外を追加して、自動調査から除外されるファイルを制御します。
keywords: 管理、自動化、除外、ブロック、クリーン、悪意のある
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
ms.openlocfilehash: 54c0f7f67b62216eae4264c8e7a55c0e34c82fb0
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166124"
---
# <a name="manage-automation-folder-exclusions"></a>自動化フォルダーの除外を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Automation フォルダーの除外を使用すると、自動調査がスキップするフォルダーを指定できます。

スキップするフォルダーに関する次の属性を制御できます。

- **フォルダー**: スキップするフォルダーとそのサブフォルダーを指定できます。

  > [!NOTE]
  > 現時点では、ディレクトリ下のファイルを除外する方法としてのワイルドカードの使用はまだサポートされていません。

- **ファイルの拡張子**: 特定のディレクトリで除外する拡張子を指定できます。 拡張機能は、攻撃者が除外されたフォルダーを使用して悪用を隠すのを防ぐ方法です。 拡張機能は、無視するファイルを明示的に定義します。

- **ファイル名**: 特定のディレクトリで除外するファイル名を指定できます。 この名前は、攻撃者が除外されたフォルダーを使用して悪用を隠すのを防ぐ方法です。 名前は、無視するファイルを明示的に定義します。

## <a name="add-an-automation-folder-exclusion"></a>オートメーション フォルダーの除外を追加する

1. ナビゲーション ウィンドウで、[**Endpoints** \> **Rules** \> **Automation] フォルダーの除外****設定**\>選択します。

2. [ **新しいフォルダーの除外**] をクリックします。

3. フォルダーの詳細を入力します。

    - フォルダー
    - 拡張機能
    - ファイル名
    - 説明

4. [**保存**] をクリックします。

> [!NOTE]
> 除外されたファイルを収集または調べるライブ応答コマンドは、"File is excluded" というエラーで失敗します。 さらに、自動調査では除外された項目は無視されます。

## <a name="edit-an-automation-folder-exclusion"></a>オートメーション フォルダーの除外を編集する

1. ナビゲーション ウィンドウで、[**Endpoints** \> **Rules** \> **Automation] フォルダーの除外****設定**\>選択します。
2. フォルダーの除外で **[編集]** をクリックします。
3. ルールの詳細を更新し、[保存] をクリック **します**。

## <a name="remove-an-automation-folder-exclusion"></a>オートメーション フォルダーの除外を削除する

1. ナビゲーション ウィンドウで、[**Endpoints** \> **Rules** \> **Automation] フォルダーの除外****設定**\>選択します。
2. [ **除外の削除]** をクリックします。

## <a name="related-topics"></a>関連項目

- [自動化が許可/ブロックされたリストを管理する](manage-indicators.md)
- [自動化ファイルのアップロードを管理する](manage-automation-file-uploads.md)
