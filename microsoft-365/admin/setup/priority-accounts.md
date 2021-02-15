---
title: 優先度アカウントの管理と監視
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
description: ビジネスに大きな影響を与えるアカウントとの間で送信された電子メール メッセージと遅延したメッセージを監視します。
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233364"
---
# <a name="manage-and-monitor-priority-accounts"></a>優先度アカウントの管理と監視

すべての Microsoft 365 組織には、役員、リーダー、マネージャー、機密性の高い、独自の情報、または優先度の高い情報にアクセスできるその他のユーザーなど、重要なユーザーがいます。

組織でこれらのアカウントを保護するために、特定のユーザーを優先度アカウントとして指定し、追加の保護を提供するアプリ固有の機能を活用できます。 今後、より多くのアプリと機能が優先度アカウントをサポートし、最初に、優先度アカウント保護とプレミアム メールフロー監視の 2 つの機能を **発表しました**。

- **優先度アカウント** 保護 - microsoft Defender for Office 365 (以前の Office 365 Advanced Threat Protection) は、アラート、レポート、調査のフィルターで使用できるタグとして優先度アカウントをサポートします。 詳細については [、Microsoft Defender の User タグで 365 Office確認](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)してください。
- **プレミアム メール フロー監視** - 正常なメール フローはビジネスの成功に不可欠であり、配信の遅延や失敗はビジネスに悪影響を与える可能性があります。 失敗または遅延したメールのしきい値を選択し、そのしきい値を超えた場合にアラートを受信し、優先度アカウントのメールの問題のレポートを表示できます。 詳細については、最新の [EAC で優先度アカウント レポートのメールの問題を確認してください。](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

優先度アカウントのセキュリティのベスト プラクティスについては、「優先度アカウントの [セキュリティに関する推奨事項」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)。

## <a name="before-you-begin"></a>はじめに

この **トピックで説明する** 優先度アカウント保護機能は、次の要件を満たす組織でのみ使用できます。

- Office 365 E3、Office 365 E5、Microsoft 365 E5、または Microsoft 365 E5 Security を含む Office 365 プラン 2 用の Microsoft Defender。

この **トピックで説明する** プレミアム メール フロー監視機能は、次の要件を満たす組織でのみ使用できます。

- 組織のライセンス数が 10,000 以上である必要があります。ライセンス数は、Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 のいずれか、または組み合わせのいずれかです。 たとえば、対象となる製品から合計 11,500 ライセンスの場合、組織は 3000 Office 365 E3 ライセンスと 8500 Microsoft 365 E5 を持ちます。
- 組織に月間 50 人以上のアクティブな Exchange Online ユーザーが必要です。

> [!NOTE]
> 最大 250 の優先度アカウントを監視できます。

### <a name="add-priority-accounts-from-the-setup-page"></a>[セットアップ] ページから優先度アカウントを追加する

[セットアップ] ページから優先度アカウント **を追加します**。

1. Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. [組織の知識  >  **のセットアップ]** に移動し、[最も重要なアカウントの監視] で [**表示] を選択します**。

3. [開始 **] または [管理]** を **選択します**。

4. [優先度 **アカウントの追加** ] ページの検索フィールドに、優先度アカウントリストに追加するユーザーの名前または電子メール アドレスを入力します。 メールの失敗または遅延に関するしきい値を設定し、優先度アカウントの問題に関する週単位のレポートを取得することもできます。

5. ユーザーを選択し、[保存] を **選択します**。

[アクティブなユーザー] ページから優先度アカウントを追加することもできます。

### <a name="add-priority-accounts-from-active-users-page"></a>[アクティブ なユーザー] ページから優先度アカウントを追加する

[アクティブなユーザー] ページから優先度アカウントを追加します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。

2. [アクティブ **なユーザー**  >  **] に移動し**、ページの上部にある **[...]** を選択します。 [優先度アカウント **の管理] を選択します**。

3. [**アカウントの追加**] を選択し、[優先度アカウントの追加] ページの検索フィールドに、優先度アカウントの一覧に追加するユーザーの名前を入力します。

4. ユーザーを選択し、[保存] を **選択します**。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>優先度アカウントの一覧からユーザーを削除する

1. Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. [組織の知識  >  **のセットアップ]** に移動し、[最も重要なアカウントの監視] で [**表示] を選択します**。

3. On the **Monitor your most accounts** page, choose Priority **accounts** under Manage **this feature**.

4. [優先度 **アカウント] ページ** で、一覧から削除するユーザーを選択し、[アカウントの削除] を **選択します**。

## <a name="related-topics"></a>関連項目

[Microsoft 365 での優先度アカウントの使用](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)