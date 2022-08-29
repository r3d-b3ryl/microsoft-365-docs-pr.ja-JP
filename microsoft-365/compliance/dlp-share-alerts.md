---
title: DLP アラートを共有する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: 調査のための最小限のアクセス許可を持つユーザーにデータ損失防止アラートを共有する方法について説明します。
ms.openlocfilehash: 81336701a732a11e8ebd1b76e2e49ed758c00139
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360619"
---
# <a name="share-data-loss-prevention-alerts-preview"></a>データ損失防止アラートの共有 (プレビュー)

[適切なアクセス許可](dlp-configure-view-alerts-policies.md#roles)を持つユーザーは、DLP アラート コンソールでMicrosoft Purview データ損失防止 (DLP) アラートを表示できます。 ただし、アラートのトリアージと調査が行われるので、DLP とアラート コンソールに対する完全なアクセス許可を持っていない他のユーザーと共有する必要がある場合があります。

この記事の手順を使用するための制限付きアクセス許可を付与するアラートをユーザーと共有できます。

## <a name="before-you-begin"></a>はじめに

DLP アラートに慣れていない場合は、「 [データ損失防止ポリシーのアラートを構成して表示する](/microsoft-365/compliance/dlp-configure-view-alerts-policies)」を参照してください。

この手順では、Purview のカスタムロール グループを作成する必要があります。 Microsoft Purview でアクセス許可、ロール、ロール グループを操作していない場合は、[Microsoft Purview コンプライアンス ポータルのアクセス許可に関するページを](/microsoft-365/compliance/microsoft-365-compliance-center-permissions)参照してください。 

## <a name="configure-dlp-alert-urls-for-review"></a>レビュー用に DLP アラート URL を構成する

1. グローバル [管理](https://compliance.microsoft.com)アクセス許可を持つアカウントでMicrosoft Purview コンプライアンス ポータルを開きます。

1. アラートを共有するユーザーの [カスタム ロール グループ](/microsoft-365/compliance/microsoft-365-compliance-center-permissions#create-a-custom-role-group) を作成します。 たとえば、`DLPAlertInvestigator` となります。 これらのロールをグループに追加します。
    1. **表示専用 DLP コンプライアンス管理** - 必須。
    1. **データ分類コンテンツ ビューアー** - 必須。
    1. **プレビュー** - *このロールは省略可能です*。校閲者がソース コンテンツを表示する必要がある場合は、これを割り当てます。

1. この例 `DLPAlertInvestigator`では、作成したカスタム ロール グループにユーザーを追加します。

1.  **[DLP アラート]** タブを開き、共有するアラートを選択します。 ポップアップ ウィンドウが開きます。

1. アラートの **アラート ID** と **検出時刻** の値を取得します。

![DLP アラートの詳細を示す画像](../media/dlp-alert-details1.png)

6. [ **検出された時刻** ] フィールドの値は、ローカル時刻です。 パラメーターで使用するには、その値を UTC 時刻に変換する `creationtime` 必要があります。 インターネット検索を使用して、ローカルから UTC の時間コンバーターが多数用意されています。

7. 次の形式で共有可能な URL を作成します。

`<compliance-portal-domain>/datalossprevention/alerts/eventdeeplink?eventid={eventId}&creationtime={creationTime}`
  
例:
 
`compliance.microsoft.com/datalossprevention/alerts/eventdeeplink?eventid=1eae3e53-c045-1c9b-ee00-08da7a6751dc&creationtime=2022-08-10T12:30:00Z`

この例では、 **検出された時刻** の値は **、2022 年 8 月 9 日午後 5 時 30 分** の太平洋夏時間です。 これにより **、UTC または 8 月 10 日の午前 12 時 30 分** (UTC) に変換されます。 `2022-08-10T12:30:00Z`

8. このリンクは、作成したグループ内のユーザーと共有できます。そのユーザーは、確認と調査のためにアラートにアクセスできます。

