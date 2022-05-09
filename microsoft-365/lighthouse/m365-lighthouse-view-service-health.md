---
title: Microsoft 365 Lighthouseでテナント サービスの正常性を表示する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、テナント サービスの正常性を表示する方法について説明します。
ms.openlocfilehash: 8ad96c77f14148fefd6d00cd51af093cd081d857
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "65187824"
---
# <a name="view-tenant-service-health-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseでテナント サービスの正常性を表示する

Microsoft 365 Lighthouseで管理するテナントのサービス正常性を表示できます。 サービス正常性には、Microsoft Intune、Azure Active Directory (Azure AD) ID サービス、モバイル デバイス管理 (MDM) クラウド サービスなど、いくつかのサービスのインシデントとアドバイザリが含まれます。 また、インシデントの影響を受けるマネージド テナントの数も確認できます。 たとえば、いずれかのテナントで問題が発生している場合は、サービス正常性 ページを確認して、進行中の解決策に関する既知の問題か、最近の変更が影響を与えている可能性があるかどうかを判断できます。 これにより、トラブルシューティングにかかる時間が短縮され、サポートの呼び出しが減る可能性があります。

Lighthouse にサインインできない場合は、[Microsoft 365 サービスの正常性状態ページ](https://status.office365.com/)を使用して、パートナー テナントにログインできない既知の問題を確認できます。 また、Twitter で [@MSFT365status](https://twitter.com/MSFT365Status) に従ってサインアップし、特定のサービス インシデントに関する情報を表示します。

## <a name="before-you-begin"></a>開始する前に

サービスの正常性を表示するには、**microsoft.office365.serviceHealth/allEntities/allTasks** というプロパティセットを持つパートナー テナントのAzure AD ロールが必要です。 Azure AD ロールの一覧については、[組み込みロールAzure AD](/azure/active-directory/roles/permissions-reference)参照してください。

## <a name="view-service-health-status-for-all-tenants"></a>すべてのテナントのサービス正常性状態を表示する

1. Lighthouse の左側のナビゲーション ウィンドウで、**サービス正常性** を選択します。

2. **サービス正常性** ページで、次のような現在のサービス正常性状態を確認します。

   - インシデントの合計数
   - マネージド テナントに影響を与えるアドバイザリの合計数
   - アクティブなインシデントを含むサービスの数。

3. [ **すべてのサービス** ] タブで、サービスごとの問題を確認します。

4. [ **すべての問題** ] タブで、現在のすべての問題を確認します。

## <a name="review-issue-details"></a>問題の詳細を確認する

1. Lighthouse の左側のナビゲーション ウィンドウで、**サービス正常性** を選択します。

2. **[サービス正常性**] ページで、[**すべてのサービス**] または [**すべての問題**] タブを選択します。

3. 一覧から問題を選択します。

4. 問題の詳細ウィンドウで、問題の種類、影響を受けたテナント、ユーザーの影響、問題の履歴など、詳細な情報を確認します。

[ **テナントの影響を受ける** ] タブで、影響を受けるテナントの一覧をコンマ区切り値 (.csv) ファイルにエクスポートして、サポート チームと共有できます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365サービスの正常性を確認する方法](/microsoft-365/enterprise/view-service-health) (記事)\
[Microsoft 365 Lighthouseに関する既知の問題](m365-lighthouse-known-issues.md) (記事)\
[Microsoft 365 LighthouseでAzure Active Directory ロールを表示する](m365-lighthouse-view-your-roles.md) (記事)
