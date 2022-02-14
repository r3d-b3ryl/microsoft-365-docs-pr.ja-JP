---
title: テナント サービスの正常性の表示
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
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseの正常性を表示する方法について説明します。
ms.openlocfilehash: b7361865e0ad3f070e128207a92669f3515e9969
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62466155"
---
# <a name="view-tenant-service-health"></a>テナント サービスの正常性の表示

> [!NOTE]
> この記事で説明する機能はプレビュー段階であり、変更される可能性があり、[要件](m365-lighthouse-requirements.md)を満たすパートナーのみが利用できます。 組織に Microsoft 365 Lighthouse がない場合は、「[Microsoft 365 Lighthouse にサインアップする](m365-lighthouse-sign-up.md)」を参照してください。

管理するテナントのサービス正常性は、Microsoft 365 Lighthouse。 サービス正常性には、Microsoft Intune、Azure Active Directory (Azure AD) ID サービス、モバイル デバイス管理 (MDM) クラウド サービスなど、いくつかのサービスのインシデントとアドバイザリが含まれます。 また、インシデントの影響を受ける管理対象テナントの数も確認できます。 たとえば、テナントの 1 つで問題が発生している場合は、[サービスの正常性] ページを確認して、進行中の解決に関する既知の問題かどうか、または最近の変更が問題に影響を与えているかどうかを確認できます。 これにより、トラブルシューティングに時間を節約し、サポート呼び出しを削減できます。

ライトハウスにサインインできない場合は、[Microsoft 365](https://status.office365.com/) サービスの正常性状態ページを使用して、パートナー テナントにログインできない既知の問題を確認できます。 また、サインアップして [Twitter の@MSFT365status](https://twitter.com/MSFT365Status) 特定のサービス インシデントに関する情報を確認します。

## <a name="before-you-begin"></a>開始する前に

サービスの正常性を表示するには、**microsoft.office365.serviceHealth/allEntities/allTasks** というプロパティ セットを持つパートナー テナントの Azure AD ロールが必要です。 役割の一覧についてはAzure AD組み込[Azure ADを参照してください](/azure/active-directory/roles/permissions-reference)。

## <a name="view-service-health-status-for-all-tenants"></a>すべてのテナントのサービス正常性状態の表示

1. ライトハウスの左側のナビゲーション ウィンドウで、[サービスの正常性] **を選択します**。

2. [サービス **正常性] ページで** 、次のサービス正常性状態を確認します。

   -   インシデントの総数
   -   管理テナントに影響を与えるアドバイザリの総数
   -   アクティブなインシデントを含むサービスの数。

3. [すべての **サービス] タブ** で、サービス別に問題を確認します。

4. [すべての **問題] タブで** 、現在のすべての問題を確認します。

## <a name="review-issue-details"></a>問題の詳細を確認する

1. ライトハウスの左側のナビゲーション ウィンドウで、[サービスの正常性] **を選択します**。

2. [サービス **の正常性] ページ** で、[すべてのサービス **] または [すべての問題****] タブを選択** します。

3. リストから問題を選択します。

4. [問題の詳細] ウィンドウで、問題の種類、影響を受けるテナント、ユーザーへの影響、発行履歴などの詳細情報を確認します。

[影響 **を受ける** テナント] タブで、影響を受けるテナントの一覧を共通の値 (.cvs) ファイルにエクスポートして、サポート チームと共有できます。

## <a name="related-content"></a>関連コンテンツ
[サービスの正常性Microsoft 365する方法](/microsoft-365/enterprise/view-service-health) (記事)
