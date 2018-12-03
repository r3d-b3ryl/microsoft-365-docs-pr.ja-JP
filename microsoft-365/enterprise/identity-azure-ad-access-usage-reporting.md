---
title: '手順 13: テナントとサインイン アクティビティを監視する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD のアクセスと利用状況レポートについて理解し、構成します。
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868985"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a>手順 13: テナントとサインイン アクティビティを監視する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、Azure AD のレポートを使用して監査ログおよびサインイン アクティビティを確認します。2 種類のレポートを利用できます。

**監査ログ アクティビティ レポート**には、Azure AD テナントで実行されたすべてのタスクの履歴が記録されます。このレポートから、次のような情報を確認できます。

- 管理者グループにユーザーを追加したユーザー
- 特定のアプリにサインインしたユーザー
- パスワード リセットの実行回数

**サインイン アクティビティ レポート**には、監査ログ レポートで報告されたタスクを実行したユーザーが記録されます。このレポートから、次のような情報を確認できます。

- 調査中の特定のユーザーのサインイン パターン
- 日、週、月あたりのサインインの回数
- 失敗したサインインの回数とそのアカウント

レポートとレポートへのアクセス方法の詳細については、「[Azure Active Directory レポート](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)」を参照してください。

この手順を実行すると、これらのレポートを認識でき、また計画とセキュリティの目的でレポートを使用して Azure AD のイベントとアクティビティに関する情報を把握する方法を理解できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [ユーザーが各自のグループを作成および管理できるようにする](identity-self-service-group-management.md) |
