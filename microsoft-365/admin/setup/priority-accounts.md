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
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
description: ビジネスに大きな影響を与えるアカウントとの間で送信される、失敗したメールメッセージと遅延メール メッセージを監視します。
ms.openlocfilehash: 4ade66d811fd63cbf7bb28d254f21ee454741f13
ms.sourcegitcommit: a7b289b8cc3a2eb79d5e46f20f2968adc0237da1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58394602"
---
# <a name="manage-and-monitor-priority-accounts"></a>優先アカウントを管理および監視する

すべての組織Microsoft 365、機密情報、専有情報、または優先度の高い情報にアクセスできるエグゼクティブ、リーダー、マネージャー、その他のユーザーなど、不可欠なユーザーがいます。

組織がこれらのアカウントを保護するために、特定のユーザーを優先度アカウントとして指定し、追加の保護を提供するアプリ固有の機能を活用できます。 今後、より多くのアプリと機能が優先アカウントをサポートし、まず、優先度アカウント保護とプレミアム メール フロー監視の 2 つの機能を **発表しました**。

- **優先度アカウント保護**- Microsoft Defender for Office 365 (以前は Office 365 Advanced Threat Protection) は、アラート、レポート、調査のフィルターで使用できるタグとして優先度アカウントをサポートします。 詳細については[、「Microsoft Defender の User tags for Office 365」 を参照してください](../../security/office-365-security/user-tags.md)。

  自然な質問は、「すべてのユーザーが優先事項ではありませんか? すべてのユーザーを優先アカウントとして指定しない理由 はい、すべてのユーザーが優先事項ですが、優先度アカウント保護には次のような追加の利点があります。

  - **その他のヒューリスティック**: Microsoft データセンター内のメール フローの分析は、会社の役員のメール フロー パターンが平均的な従業員とは異なっているという点を示しています。 優先度アカウント保護は、通常の従業員に利益を得ない会社の役員に合わせて特別に調整された追加のヒューリスティックを提供します。
  - **レポートのその他の可視性**: 実際には、すべてのユーザー (または影響を受けるすべてのユーザー) の情報は、アラート、レポート、および調査で既に利用できます。 優先度アカウント タグをフィルターとして使用すると、調査を具体的にターゲットに設定できます。

- **プレミアムメール Flow監視**- 正常なメール フローはビジネスの成功にとって重要であり、配信の遅延や失敗はビジネスに悪影響を及ぼす可能性があります。 失敗または遅延メールのしきい値を選択し、そのしきい値を超えたときにアラートを受信し、優先アカウントの電子メールの問題のレポートを表示できます。 詳細については、「最新の EAC で優先度アカウントの電子メールの [問題」レポートを参照してください。](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

優先度アカウントのセキュリティのベスト プラクティスについては、「優先度アカウント [のセキュリティに関する推奨事項」を参照してください](../../security/office-365-security/security-recommendations-for-priority-accounts.md)。

## <a name="before-you-begin"></a>はじめに

この **トピックで説明する** 優先度アカウント保護機能は、次の要件を満たす組織でのみ使用できます。

- Microsoft Defender for Office 365 プラン 2(Office 365 E3、Office 365 E5、Microsoft 365 E5、またはMicrosoft 365 E5 Security。

この **プレミアムでFlow** メール 監視機能は、次の要件を満たす組織でのみ使用できます。

- 組織では、Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 のいずれかの製品、または組み合わせのいずれかから、少なくとも 5,000 のライセンス数を持っている必要があります。 たとえば、組織は Office 365 E3 のライセンスを 3,000 個と Microsoft 365 E5 のライセンスを 2,500 個持つことで、条件を満たす製品から合計 5,500 個のライセンスを持つことができます。
- 組織に月間 50 人以上のアクティブな Exchange Online ユーザーが必要です。

> [!NOTE]
> 最大 250 の優先度アカウントを監視できます。

メールボックスに優先度アカウント保護を適用する場合は、メールボックスにアクセスできるユーザー (CEO や CEO の予定表を管理する CEO のエグゼクティブ アシスタントなど) にも優先度アカウント保護を適用する必要があります。

### <a name="add-priority-accounts-from-the-setup-page"></a>[セットアップ] ページから優先度アカウントを追加する

[セットアップ] ページから優先度アカウント **を追加します**。

1. で、Microsoft 365 管理センターに移動します <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. [組織の **ナレッジの**  >  **セットアップ] に移動** し、[最も **重要** なアカウントの監視] で [表示 **] を選択します**。

3. [管理 **はじめに] または [** 管理]**を選択します**。

4. [優先度 **アカウントの追加** ] ページの検索フィールドに、優先度アカウントリストに追加するユーザーの名前または電子メール アドレスを入力します。 また、失敗または遅延メールのメールしきい値を設定し、優先アカウントの問題に関する週次レポートを取得することもできます。

5. ユーザーを選択し、[保存] を **選択します**。

[アクティブ ユーザー] ページから優先度アカウントを追加することもできます。

### <a name="add-priority-accounts-from-active-users-page"></a>[アクティブ ユーザー] ページから優先度アカウントを追加する

[アクティブ ユーザー] ページから優先度アカウントを追加します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

2. [ユーザー ]  >  **[アクティブなユーザー** ] に移動し、ページの上部にある 3 つのドット (その他のアクション) を選択します。 [優先度 **アカウントの管理] を選択します**。

3. [**アカウントの追加]** を選択し、[優先度アカウントの追加] ページの検索フィールドに、優先度アカウントリストに追加するユーザーの名前を入力します。

4. ユーザーを選択し、[保存] を **選択します**。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>優先度アカウントリストからユーザーを削除する

1. で、Microsoft 365 管理センターに移動します <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. [組織の **ナレッジの**  >  **セットアップ] に移動** し、[最も **重要** なアカウントの監視] で [表示 **] を選択します**。

3. [最も **多くのアカウントを監視する** ] ページで、[この機能の管理] **で** [優先度アカウント **] を選択します**。

4. [優先度アカウント **] ページ** で、リストから削除するユーザーまたはユーザーを選択し、[アカウントの削除] **を選択します**。

## <a name="related-topics"></a>関連項目

[サーバーでの優先度アカウントのMicrosoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
