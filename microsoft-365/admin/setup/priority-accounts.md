---
title: 優先度アカウントを管理および監視する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: ビジネスへの影響が大きいアカウントによって送受信された、失敗した電子メールメッセージと遅延した電子メールメッセージを監視します。
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477615"
---
# <a name="manage-and-monitor-priority-accounts"></a>優先度アカウントを管理および監視する

Microsoft のすべての365組織には、経営幹部、リーダー、マネージャー、または機密性の高い、機密、または高優先度の情報にアクセスできるその他のユーザーなど、重要な人物がいます。

組織でこれらのアカウントを保護するために、特定のユーザーを優先度のアカウントとして指定し、アプリ固有の機能を利用して、その他の保護を強化することができます。 将来的には、優先度の高いアカウントをサポートするアプリや機能が増え、次のように、 **優先度のアカウント保護** と **プレミアムメールフローの監視** という2つの機能が発表されました。

- **Priority account protection** -Microsoft Defender for office 365 (旧称 Office 365 Advanced Threat protection) は、警告、レポート、および調査のフィルターで使用できるタグとして、優先度アカウントをサポートします。 詳細については、「 [Microsoft Defender For Office 365」の「User tags」](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)を参照してください。
- **プレミアムメールフローの監視** -正常なメールフローがビジネスの成功にとって重要であり、配信の遅延または失敗がビジネスに悪影響を与える可能性があります。 失敗または遅延しているメールのしきい値を選択し、しきい値を超えたときに通知を受信し、優先度アカウントの電子メールの問題に関するレポートを表示することができます。 詳細については、 [モダン EAC で、優先アカウントレポートに関するメールの問題](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)を確認してください。

## <a name="before-you-begin"></a>開始する前に

このトピックに記載されている **優先度のアカウント保護** 機能は、次の要件を満たす組織でのみ使用できます。

- Microsoft Defender for Office 365 プラン 2 (Office 365 E3、Office 365 E5、Microsoft 365 E5、Microsoft 365 E5 セキュリティを含む)。

このトピックに記載されている **プレミアムメールフロー監視** 機能は、次の要件を満たしている組織にのみ使用できます。

- 組織のライセンス数は、少なくとも1万である必要があります。これは、Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 のいずれかまたは両方から構成されている必要があります。 たとえば、組織は 3000 Office 365 E3 ライセンスと 8500 Microsoft 365 E5 を持つことができます。これには、正規の製品に対する合計の11500ライセンスが含まれています。
- 組織には、少なくとも50のアクティブな Exchange Online ユーザーが必要です。

> [!NOTE]
> 最大250の優先度のアカウントを監視できます。

### <a name="add-priority-accounts-from-the-setup-page"></a>セットアップページから優先度アカウントを追加する

[ **セットアップ] ページ** で、優先度の高いアカウントを追加します。

1. Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。

2. [**セットアップ**  >  **の組織ナレッジ**] に移動して、[**最も重要なアカウントを監視** する] の下にある [**表示**] を選択します。

3. [ **開始** ] または [ **管理**] を選択します。

4. [ **優先度アカウントの追加** ] ページで、検索フィールドに、優先度アカウントリストに追加するユーザーの名前または電子メールアドレスを入力します。 また、失敗したメールまたは遅延したメールのメールのしきい値を設定して、優先度アカウントの問題の週単位のレポートを取得することもできます。

5. ユーザーを選択して、[ **保存**] を選択します。

[アクティブなユーザー] ページから優先度の高いアカウントを追加することもできます。

### <a name="add-priority-accounts-from-active-users-page"></a>[アクティブなユーザー] ページから優先度のアカウントを追加する

[アクティブなユーザー] ページから優先度の高いアカウントを追加します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。

2. [アクティブ **なユーザー] に移動** して、  >  **Active users** ページの上部にある [.. **.** ] を選択します。 [ **優先度アカウントの管理**] を選択します。

3. [ **アカウントの追加**] を選択し、[ **優先度アカウントの追加** ] ページの検索フィールドに、優先度のアカウント一覧に追加するユーザーの名前を入力します。

4. ユーザーを選択して、[ **保存**] を選択します。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>優先順位のアカウントリストからユーザーを削除する

1. Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。

2. [**セットアップ**  >  **の組織ナレッジ**] に移動して、[**最も重要なアカウントを監視** する] の下にある [**表示**] を選択します。

3. [**大部分のアカウントの監視**] ページで、[**この機能の管理**] の [**優先度の高いアカウント**] を選択します。

4. [ **優先度アカウント** ] ページで、リストから削除するユーザーを選択し、[ **アカウントの削除**] を選択します。

## <a name="related-topics"></a>関連トピック

[Microsoft 365 での優先度アカウントの使用](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)