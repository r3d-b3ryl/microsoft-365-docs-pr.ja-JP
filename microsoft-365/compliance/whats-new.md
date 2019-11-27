---
title: Microsoft 365 コンプライアンスセンターの新機能
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Microsoft 365 コンプライアンスセンターに新機能を継続的に追加し、学習した問題を修正し、フィードバックに基づいて変更を加えています。 今月の内容を確認してください。
ms.openlocfilehash: c9ed6e6d7f1489a510283a344094754a6f8cdeb4
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615667"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Microsoft 365 コンプライアンスセンターの新機能

[Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)に新機能を継続的に追加し、学習した問題を修正し、フィードバックに基づいて変更を加えています。 お客様が現在利用できるものを確認するには、次のようにしてください。 一部の機能は、お客様のさまざまなスピードでロールアウトされます。 機能がまだ表示されていない場合は、[対象のリリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)に追加してみてください。

> [!TIP]
> 他の管理センターでは何が起こっているのでしょうか。 次の記事をご覧ください。<br>[Microsoft 365 管理センターの新機能](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 管理センターの新機能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)

## <a name="september-2019"></a>2019 年 9 月

今月リリースのリリース前に静かになる理由をご確認ください。 マイクロソフトは、11月に[Microsoft Ignite](https://www.microsoft.com/ignite)で最近される新しい革新的なコンプライアンスソリューションの構築に取り組んでいます。 引き続きご調整ください。

### <a name="new-encryption-options-for-sensitivity-labels"></a>機密ラベルの新しい暗号化オプション 

機密ラベルの暗号化を構成する場合、次の2つのオプションがあるので、ユーザーはラベルを電子メールやドキュメントに手動で適用するときにアクセス許可を割り当てることができます。<br>
- **Outlook 電子メール**にラベルを適用する場合、ユーザーは [転送不可] オプションに相当する制限を適用できます。 受信者は、メッセージを読み取ることはできますが、コンテンツを転送、印刷、またはコピーすることはできません。
- **Word、PowerPoint、Excel**の各ファイルにラベルを適用すると、ユーザーは特定のユーザーやグループにアクセス許可を割り当てるように求められます。

[詳細情報](encryption-sensitivity-labels.md#let-users-assign-permissions)

## <a name="august-2019"></a>2019 年 8 月

### <a name="update-to-data-investigations"></a>データ調査への更新

データの調査を実行すると、元の場所からアイテムを削除できるようになります。 これは、組織全体の Exchange メールボックス、SharePoint サイト、および OneDrive アカウントからアイテムを削除できることを意味します。 アイテムを証拠として収集したため、証拠セットに保存されたアイテムのコピーが、さらに参考になるか、参照として保持することができます。 [詳細情報](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) 

## <a name="july-2019"></a>2019 年 7 月

### <a name="new-admin-roles"></a>新しい管理者の役割

組織のセキュリティとコンプライアンスを管理するために、2つの新しい管理者の役割をリリースしました。すべての友人に連絡します。

- **コンプライアンスデータ管理者**。この役割を持つユーザーは、Microsoft 365 コンプライアンスセンター、Microsoft 365 管理センター、および Azure のデータを保護および追跡するためのアクセス許可を持っています。 また、Exchange 管理センター、コンプライアンスマネージャー、Teams & Skype for Business 管理センターを管理したり、Azure および Microsoft 365 のサポートチケットを作成したりすることもできます。
- **セキュリティオペレーター**。 この役割を持つユーザーは、通知を管理し、Microsoft 365 セキュリティセンター、Azure Active Directory、Id 保護、特権 Id 管理、および Office 365 Security & コンプライアンスセンターのすべてを含む、セキュリティ関連機能へのグローバルな読み取り専用アクセスを持つことができます。

[これらの役割の詳細情報](https://docs.microsoft.com/microsoft-365/security//office-365-security/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>レポートの検索とフィルター処理

必要なレポートを見つけるために、大量のレポートをスクロールする必要はありません。 これで、(タイトルに基づいて) レポートを検索し、「ラベル」や「コンプライアンス」、「Office 365」や「Microsoft Cloud App Security」などのソースのカテゴリにフィルターを適用することができます。

![適用されたフィルターを使用したレポートの検索とフィルターのボタンの画面キャプチャ](media/mcc_report_filtering.png)
