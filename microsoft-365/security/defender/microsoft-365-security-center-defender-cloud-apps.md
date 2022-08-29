---
title: Microsoft 365 DefenderのMicrosoft Defender for Cloud Apps (プレビュー)
description: Microsoft Defender for Cloud AppsからMicrosoft 365 Defenderへの変更について説明します
keywords: Microsoft 365 Defenderの概要、Microsoft Defender for Cloud Apps
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dacurwin
author: dcurwin
manager: dansimp
ms.date: 08/21/2022
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 13d178f77efa19ed53c93afa454ddaf6e481a8a6
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67408421"
---
# <a name="microsoft-defender-for-cloud-apps-in-microsoft-365-defender-preview"></a>Microsoft 365 DefenderのMicrosoft Defender for Cloud Apps (プレビュー)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Cloud Apps](/defender-cloud-apps/)

Microsoft Defender for Cloud AppsがMicrosoft 365 Defenderの一部になりました。 Microsoft 365 Defender ポータルを使用すると、セキュリティ管理者は 1 つの場所でセキュリティ タスクを実行できます。 これにより、ワークフローが簡略化され、他のMicrosoft 365 Defender サービスの機能が追加されます。 Microsoft 365 Defenderは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するためのホームです。

SOC アナリストは、クラウド アプリを含むすべてのMicrosoft 365 Defenderワークロードをトリアージ、調査、およびハントできます。
Defender for Cloud Apps アラートはMicrosoft 365 Defenderのインシデント キューとアラート キューに引き続き表示されますが、Microsoft 365 Defender ポータルで使用可能なアラート ページ内の関連コンテンツが、各アラートの種類に適切に適応した統合形式で表示されるようになりました。

Microsoft 365 Defenderを見てみましょう<https://security.microsoft.com>。

利点の詳細については、「[Microsoft 365 Defenderの概要](microsoft-365-defender.md)」をご覧ください。

## <a name="quick-reference"></a>クイック リファレンス

次の図と表は、Microsoft Defender for Cloud AppsとMicrosoft 365 Defender間のナビゲーションの変更の一覧です。

> [!NOTE]
> 一部のページはまだ移行されておらず、Defender for Cloud Apps ポータルからアクセスする必要があります。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/defender-cloud-apps-m365-defender.png" alt-text="Microsoft 365 Defender ポータルの新しい場所" lightbox="../../media/defender-cloud-apps-m365-defender.png":::

| Defender for Cloud Apps | Microsoft 365 Defender |
|---------|---------|
| Cloud Discover ダッシュボード | クラウド アプリ -> Cloud Discovery |
| 検出されたアプリ | [Cloud Discovery] ページの [タブ] |
| 検出されたリソース | [Cloud Discovery] ページの [タブ] |
| IP アドレス | [Cloud Discovery] ページの [タブ] |
| ユーザー | [Cloud Discovery] ページの [タブ] |
| デバイス | [Cloud Discovery] ページの [タブ] |
| クラウド アプリ カタログ |  クラウド アプリ -> Cloud アプリ カタログ |
| Cloud Discovery スナップショット レポートを作成する | [Cloud Discovery] ページの [アクション] |
| アクティビティ ログ | クラウド アプリ -> アクティビティ ログ |
| Files | Defender for Cloud Apps ポータルの残り |
| ユーザーとアカウント | 資産 -> ID |
| セキュリティ構成 | Defender for Cloud Apps ポータルの残り |
| ID セキュリティ体制 | [Microsoft Defender for Identityの ID セキュリティ体制の評価](/defender-for-identity/isp-overview) |
| OAuth アプリ | クラウド アプリ -> OAuth アプリ |
| 接続済みアプリ | Defender for Cloud Apps ポータルの残り |

> [!NOTE]
> Microsoft 365 Defender ポータルの新しい Defender for Cloud Apps エクスペリエンスは、現在、[管理アクセスの管理](/defender-cloud-apps/manage-admins)に関するページで詳しく説明されているすべてのユーザーに対して利用できます。ただし、次を除きます。
>
> - [Defender for Cloud Apps の組み込み管理者ロール](/defender-cloud-apps/manage-admins#built-in-admin-roles-in-defender-for-cloud-apps)で定義されているように、**App/Instance** 管理者、**ユーザー グループ管理者**、**Cloud Discovery グローバル管理者**、および Cloud **Discovery レポート管理者**。
> - アクティビティのプライバシーで定義されているユーザー [プライバシー](/defender-cloud-apps/activity-privacy) グループ

## <a name="whats-changed"></a>変更内容

Defender for Cloud Apps とMicrosoft 365 Defenderの統合に伴う変更について説明します。

### <a name="global-search"></a>グローバル検索

Microsoft 365 Defenderのグローバル検索 (ページ上部の検索バーを使用) に追加の検索可能なエンティティが含まれるようになりました。これにより、Defender for Cloud Apps で接続されたアプリを検索できます。

:::image type="content" source="../../media/global-search-apps.png" alt-text="接続されているアプリを検索します。":::

### <a name="assets-and-identities"></a>資産と ID

Microsoft 365 Defenderエクスペリエンス全体にわたる専用 **アセット** セクションの作成の一環として、Defender for Cloud Apps の **[ユーザーとアカウント]** セクションが **[ID]** セクションとして再ブランド化されます。 機能の変更は必要ありません。

## <a name="related-information"></a>関連情報

- [Microsoft 365 Defender](microsoft-365-defender.md)
