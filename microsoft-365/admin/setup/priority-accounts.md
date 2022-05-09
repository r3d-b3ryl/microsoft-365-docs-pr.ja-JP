---
title: 優先アカウントを管理および監視する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
description: ビジネスに大きな影響を与えるアカウントとの間で送受信されたメール メッセージの失敗と遅延を監視します。
ms.openlocfilehash: b8762885cc54859cf927653abb14858c0094ea12
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201351"
---
# <a name="manage-and-monitor-priority-accounts"></a>優先アカウントを管理および監視する

すべてのMicrosoft 365組織には、機密性の高い、独自の、または優先度の高い情報にアクセスできる、エグゼクティブ、リーダー、マネージャー、その他のユーザーなど、不可欠なユーザーがいます。

組織でこれらのアカウントを保護するために、特定のユーザーを優先アカウントとして指定し、追加の保護を提供するアプリ固有の機能を利用できるようになりました。 今後、優先度の高いアカウントをサポートするアプリと機能が増え、最初に、 **優先度アカウント保護** と **Premium メール フローの監視** という 2 つの機能が発表されました。

- **優先度アカウント保護** - Microsoft Defender for Office 365 (以前は Advanced Threat Protection Office 365) は、アラート、レポート、および調査のフィルターで使用できるタグとして優先度アカウントをサポートします。 詳細については、[Microsoft Defender for Office 365のユーザー タグを](../../security/office-365-security/user-tags.md)確認してください。

  自然な質問は、「すべてのユーザーが優先順位ではありませんか? すべてのユーザーを優先度アカウントとして指定しないのはなぜですか? はい。すべてのユーザーが優先されますが、優先度アカウント保護には次の追加の利点があります。

  - **その他のヒューリスティック**: Microsoft データセンター内のメール フローの分析では、会社の幹部のメール フロー パターンが平均的な従業員とは異なっていることを示しています。 優先度アカウント保護では、通常の従業員にメリットを与えない会社の経営幹部向けに特別に調整された追加のヒューリスティックが提供されます。
  - **レポートの追加の可視性**: 実際には、すべてのユーザー (または影響を受けるすべてのユーザー) の情報は、アラート、レポート、および調査で既に使用できます。 優先度アカウントタグをフィルターとして使用すると、調査を具体的にターゲットに設定できます。

- **プレミアム メールFlow監視** - 正常なメール フローは、ビジネスの成功に不可欠であり、配信の遅延や失敗がビジネスに悪影響を与える可能性があります。 失敗または遅延メールのしきい値を選択したり、しきい値を超えたときにアラートを受信したり、優先度アカウントの電子メールの問題のレポートを表示したりできます。 詳細については、[最新の EAC の優先度アカウントの電子メールの問題レポートを](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)参照してください。

優先度アカウントのセキュリティのベスト プラクティスについては、「 [優先度アカウントのセキュリティに関する推奨事項」を](../../security/office-365-security/security-recommendations-for-priority-accounts.md)参照してください。

## <a name="before-you-begin"></a>開始する前に

このトピックで説明する **優先度アカウント保護機能** は、次の要件を満たす組織でのみ使用できます。

- Office 365 E3、Office 365 E5、Microsoft 365 E5、またはMicrosoft 365 E5 Securityを含むプラン 2 をMicrosoft Defender for Office 365します。

このトピックで説明する **プレミアムメールFlow監視** 機能は、次の要件を満たす組織でのみ使用できます。

- 組織のライセンス数は、Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5のいずれかまたは組み合わせて、少なくとも 5,000 である必要があります。 たとえば、組織は Office 365 E3 のライセンスを 3,000 個と Microsoft 365 E5 のライセンスを 2,500 個持つことで、条件を満たす製品から合計 5,500 個のライセンスを持つことができます。
- 組織には、1 つ以上のコア ワークロード (Teams、One Drive for Business、SharePoint Online、Exchange Online、Office アプリ) に対して、少なくとも 50 人のアクティブ ユーザーが必要です。

> [!NOTE]
> 最大 250 個の優先度アカウントを監視できます。

メールボックスに優先度アカウント保護を適用する場合は、メールボックスにアクセスできるユーザー (CEO と CEO の予定表を管理する CEO のエグゼクティブ アシスタントなど) にも優先アカウント保護を適用する必要があります。

### <a name="add-priority-accounts-from-the-setup-page"></a>[セットアップ] ページから優先度アカウントを追加する

**[セットアップ] ページ** から優先度アカウントを追加します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の Microsoft 365 管理センターに移動します。

2. **SetupOrganizational** >  ナレッジに移動し、[**最も重要なアカウントを監視** する] で [表示] を選択します。

3. **はじめに** または管理を選択 **します**。

4. [ **優先度アカウントの追加]** ページの検索フィールドに、優先度アカウントの一覧に追加するユーザーの名前または電子メール アドレスを入力します。 また、失敗または遅延したメールの電子メールしきい値を設定し、優先度アカウントの問題の週次レポートを取得することもできます。

5. ユーザーを選択し、[ **保存]** を選択します。

[アクティブなユーザー] ページから優先度アカウントを追加することもできます。

### <a name="add-priority-accounts-from-active-users-page"></a>[アクティブなユーザー] ページから優先度アカウントを追加する

[アクティブなユーザー] ページから優先度アカウントを追加します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

2. **UsersActive** >  **ユーザー** に移動し、ページの上部にある 3 つの点 (その他のアクション) を選択します。 [ **優先度アカウントの管理**] を選択します。

3. [ **アカウントの追加]** を選択し、[ **優先度アカウントの追加** ] ページの検索フィールドに、優先度アカウントの一覧に追加するユーザーの名前を入力します。

4. ユーザーを選択し、[ **保存]** を選択します。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>優先度アカウントの一覧からユーザーを削除する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の Microsoft 365 管理センターに移動します。

2. **SetupOrganizational** >  ナレッジに移動し、[**最も重要なアカウントを監視** する] で [表示] を選択します。

3. [**ほとんどのアカウントの監視**] ページで、[**この機能の管理**] で [**優先度アカウント**] を選択します。

4. [ **優先度アカウント** ] ページで、一覧から削除するユーザーを選択し、[ **アカウントの削除**] を選択します。

## <a name="related-topics"></a>関連項目

[Microsoft 365 での優先アカウント使用](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
