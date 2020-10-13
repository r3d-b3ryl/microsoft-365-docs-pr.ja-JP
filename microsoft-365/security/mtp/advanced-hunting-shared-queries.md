---
title: Microsoft Threat Protection の高度な捜索で共有クエリを使用する
description: 定義済みおよび共有クエリを使用して、脅威の捜索をすぐに開始します。 クエリを公開または組織に共有します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタム検出、スキーマ、kusto、github リポジトリ、マイクエリ、共有クエリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7cdb15be274c89bd92995b9e947489c62521c6bb
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429685"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>高度な捜索で共有クエリを使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection



[高度な捜索](advanced-hunting-overview.md)クエリは、同じ組織内のユーザー間で共有できます。 また、GitHub で公開されているクエリも検索できます。 これらのクエリを使用すると、クエリを最初から作成することなく、特定の脅威の捜索シナリオを迅速に実行できます。

![共有クエリの画像](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>クエリを保存、変更、共有する
新規または既存のクエリを保存して、自分のみアクセスできるようにしたり、組織内の他のユーザーと共有したりできます。 

1. クエリを作成または変更します。 

2. [**クエリの保存**] ドロップダウン ボタンをクリックし、[**名前を付けて保存**] を選択します。
    
3. クエリの名前を入力します。 

   ![クエリの保存の画像](../../media/advanced-hunting-save-query.png)

4. クエリを保存するフォルダーを選択します。
    - [**共有クエリ**] — 組織のすべてのユーザーに共有する
    - [**マイ クエリ**] — 自分のみアクセス可能
    
5. [**保存**] を選択します。 

## <a name="delete-or-rename-a-query"></a>クエリを削除または名前を変更する
1. 名前を変更または削除するクエリを右クリックします。

    ![削除するクエリの画像](../../media/advanced_hunting_delete_rename.png)

2. [**削除**] を選択して、削除を確認します。 または、[**名前の変更**] を選択して、クエリに新しい名前を入力ます。

## <a name="create-a-direct-link-to-a-query"></a>クエリへの直接リンクを作成する
高度な検索クエリエディターでクエリを直接開くリンクを生成するには、クエリを最終処理して、[ **共有リンク**] を選択します。

## <a name="access-queries-in-the-github-repository"></a>GitHub リポジトリ内のクエリにアクセスする  
Microsoft のセキュリティ調査員は、[GitHub の指定された公開リポジトリ](https://aka.ms/hunting-queries)で高度な捜索クエリを定期的に共有しています。 このリポジトリは投稿できます。 投稿するには、[GitHub に無料で参加](https://github.com/)してください。

>[!tip]
>また、Microsoft のセキュリティ調査員は高度な捜索クエリも提供しています。これを使用して、新たな脅威に関連するアクティビティやインジケータを特定できます。 これらのクエリは、Microsoft Defender セキュリティ センターの[脅威の分析](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)レポートの一部として提供されます。

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
