---
title: 高度なハンティングで共有クエリMicrosoft 365 Defender使用する
description: 定義済みおよび共有クエリを使用して、脅威の捜索をすぐに開始します。 クエリを公開または組織に共有します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto, github repo, マイ クエリ, 共有クエリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: d9e90d1c4e353b9ac460420867ed56632b1e5eeb
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477123"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>高度な捜索で共有クエリを使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

[高度な捜索](advanced-hunting-overview.md)クエリは、同じ組織内のユーザー間で共有できます。 また、自分だけがアクセスできるクエリを保存することもできます。 GitHub でパブリックに共有されているコミュニティ クエリも見つかります。 これらの保存されたクエリを使用すると、クエリを最初から記述しなくても、特定の脅威ハンティング シナリオを迅速に実行できます。

高度な検索の [クエリ] タブには、[ **共有クエリ**]、[ **マイ クエリ**]、[コミュニティ クエリ] のドロップダウン メニュー **があります**。 下向きの矢印を選択してメニューを展開できます。


:::image type="content" source="../../media/advanced-hunting-shared-queries-1.png" alt-text="Microsoft 365 Defender ポータルでの共有クエリ、マイ クエリ、コミュニティ クエリ" lightbox="../../media/advanced-hunting-shared-queries-1.png":::



## <a name="save-modify-and-share-a-query"></a>クエリを保存、変更、共有する
新規または既存のクエリを保存して、自分のみアクセスできるようにしたり、組織内の他のユーザーと共有したりできます。 

1. クエリを作成または変更します。 

2. [**クエリの保存**] ドロップダウン ボタンをクリックし、[**名前を付けて保存**] を選択します。
    
3. クエリの名前を入力します。 

   :::image type="content" source="../../media/shared-query-2.png" alt-text="Microsoft 365 Defender ポータルに保存される新しいクエリ" lightbox="../../media/shared-query-2.png":::

4. クエリを保存するフォルダーを選択します。
    - [**共有クエリ**] — 組織のすべてのユーザーに共有する
    - [**マイ クエリ**] — 自分のみアクセス可能
    
5. [**保存**] を選択します。 

## <a name="delete-or-rename-a-query"></a>クエリを削除または名前を変更する
1. 名前を変更または削除するクエリの右側にある 3 つのドットを選択します。

    :::image type="content" source="../../media/advanced-hunting-del-save-query.png" alt-text="Microsoft 365 Defender ポータルの [高度な検索] ページでクエリの名前を変更または削除する" lightbox="../../media/advanced-hunting-del-save-query.png":::

2. [**削除**] を選択して、削除を確認します。 または、[**名前の変更**] を選択して、クエリに新しい名前を入力ます。

## <a name="create-a-direct-link-to-a-query"></a>クエリへの直接リンクを作成する
高度な検索クエリ エディターでクエリを直接開くリンクを生成するには、クエリを終了し、[ **リンクの共有**] を選択します。

## <a name="access-community-queries-in-the-github-repo"></a>GitHub リポジトリでコミュニティ クエリにアクセスする  
Microsoft のセキュリティ調査員は、[GitHub の指定された公開リポジトリ](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/Microsoft%20365%20Defender)で高度な捜索クエリを定期的に共有しています。 このリポジトリへの投稿は、発行する前に確認されます。 投稿するには、[GitHub に無料で参加](https://github.com/)してください。

これらのクエリは、[ **コミュニティ クエリ** ] ドロップダウン メニューでも簡単に見つけることができます。

:::image type="content" source="../../media/advanced-hunting-shared-queries-2.png" alt-text="Microsoft 365 Defender ポータルのフォルダー別に整理されたコミュニティ クエリ" lightbox="../../media/advanced-hunting-shared-queries-2.png":::

コミュニティ クエリは、 *キャンペーン*、 *コレクション*、 *防御回避* などのフォルダーにグループ化されます。 クエリに関する詳細情報は、クエリ自体のインライン コメントとして提供されます。 

>[!tip]
>また、Microsoft のセキュリティ調査員は高度な捜索クエリも提供しています。これを使用して、新たな脅威に関連するアクティビティやインジケータを特定できます。 これらのクエリは、Microsoft 365 Defenderの[脅威分析](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)レポートの一部として提供されます。


## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)