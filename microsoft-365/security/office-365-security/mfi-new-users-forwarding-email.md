---
title: 新しいユーザーがメールを転送していますのインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターで新しいユーザーが電子メールの分析情報を転送して、組織内のユーザーが新しいドメインにメッセージを転送する状況を調査する方法について学習できます。
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660019"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>新しいユーザーがセキュリティ/コンプライアンス センターで電子&を転送する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


組織内の新しいユーザー アカウントが突然外部ドメインに電子メール メッセージを転送し始める場合、疑わしい場合があります。

セキュリティ **&** コンプライアンス センターで電子メールの [](https://protection.office.com)分析情報を転送する新しいドメインは、組織内で新しく作成されたユーザーが外部ドメインにメッセージを転送するときに通知します。 この状態は、侵害された管理者アカウントが新しいユーザーの作成に使用された可能性があります。 アカウントが侵害された疑いがある場合は、「侵害されたメール アカウントへの対応 [」を参照してください](responding-to-a-compromised-email-account.md)。

この分析情報は、問題が検出された場合にのみ表示され、[転送レポート] ページ [に表示](view-mail-flow-reports.md#forwarding-report) されます。

![新しいユーザーがメールを転送していますのインサイト](../../media/mfi-new-users-forwarding-email.png)

ウィジェットをクリックすると、この記事で後述するように転送変更レポートへのリンクなど、転送されたメッセージの詳細を確認できるフライアウトが表示[](#forwarding-modifications-report)されます。

![メールを転送する新しいユーザーの分析情報をクリックした後に表示される詳細フライアウト](../../media/mfi-new-users-forwarding-email-details.png)

[上位の分析情報とおすすめ] 領域 **([** レポート ダッシュボード] または [ &]) で [すべて表示] をクリックした後に、分析情報を選択すると、**この詳細ページ** に移動 \> することもできます <https://protection.office.com/insightdashboard> 。

次のセクションで **説明するように、[インサイト** に関連付けられているレポートを表示] リンクをクリックすると、転送の変更レポートに移動できます。

## <a name="forwarding-modifications-report"></a>変更レポートの転送

転送 **変更レポートには、** 組織内の送信者から自動的に転送されるメッセージに関する詳細が表示されます。

- メッセージを外部ドメインに転送する新しく作成されたアカウント。
- 組織内の他の送信者によって転送されたことがない外部ドメインにメッセージを転送するアカウント。

このような種類の転送されたメッセージは、セキュリティまたはコンプライアンスのリスクを引き起し、アカウントが侵害された可能性があります。

レポートには、最大 90 日間のデータが含まれる。 既定では、レポートには過去 7 日間のデータが表示されます。

このレポートは、メール フロー ダッシュボードまたは [レポート](mail-flow-insights-v2.md) ダッシュボードでは直接 [使用できません](view-mail-flow-reports.md)。 新しいユーザーが電子メールの分析 **情報** を転送する場合に、分析情報に関連付けられている [表示] リンクをクリックすると、次の方法でレポートにアクセスできます。

- 転送される電子 **メールの分析情報の** [新しいドメイン] の詳細にある [[転送通知] レポートのリンクをクリックします](mfi-new-domains-being-forwarded-email.md)。
- 開く <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。

### <a name="report-view-for-the-forwarding-modifications-report"></a>転送変更レポートのレポート ビュー

レポート ビューでは、次のグラフを使用できます。

- **次のデータを表示します。新しい転送ユーザー**:

  ![転送変更レポートの [新しい転送ユーザー] ビュー](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **次のデータを表示します。新しい転送ドメイン**:

  ![転送変更レポートの [新しい転送されたドメイン] ビュー](../../media/forwarding-modifications-report-new-forwarded-domains.png)

レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲****を指定できます**。

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>転送変更レポートの詳細テーブル ビュー

[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。

- **次のデータを表示します。新しい転送ユーザー**:

  - **Name**: 送信者の電子メール アドレス。
  - **転送の種類**
  - **受信者のアドレス**
  - **詳細**
  - **Count**
  - **最初の転送日**

- **次のデータを表示します。新しい転送ドメイン**:

  - **Name**: 送信者の電子メール ドメイン。
  - **転送の種類**
  - **受信者のアドレス**
  - **詳細**
  - **Count**
  - **最初の転送日**

詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲** を **指定できます**。

テーブルから行を選択すると、 **詳細のフライ** アウトが次の情報と一緒に表示されます。

- **名前**: これは、送信者のメール アドレス ([データの表示: 新しい転送ユーザー ビュー] から) または送信者のメール ドメイン ([データの表示先 **:** 新しい転送ドメイン] ビュー) のいずれかです。 
- **転送の種類**
- **[受信者]**
- **詳細**
- **Count**
- **開始日**
- **推奨事項**: ここから、リンクをクリックして、Microsoft 365 管理センターでユーザーを管理できます。

![転送変更レポートの [転送ユーザーの新規] ビューの詳細テーブルからの詳細フライアウト](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
