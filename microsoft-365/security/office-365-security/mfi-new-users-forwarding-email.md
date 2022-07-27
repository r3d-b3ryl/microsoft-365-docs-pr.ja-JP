---
title: 新しいユーザーがメールを転送していますのインサイト
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターで電子メール 分析情報を転送する新しいユーザーを使用して、組織内のユーザーが新しいドメインにメッセージを転送するタイミングを調査する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 43938a8d6648d5e0ed510ebb6badb1721bacc961
ms.sourcegitcommit: 13a1199fbfeb329da77ce87b2781d5cc77e4a201
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67037624"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターで電子メール分析情報を転送する新しいユーザー

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

組織内の新しいユーザー アカウントが突然外部ドメインに電子メール メッセージを転送し始めると、疑わしいです。

[セキュリティ & コンプライアンス センター](https://protection.office.com)で電子メール 分析情報を **転送する新しいユーザー** は、組織内の新しく作成されたユーザーが外部ドメインにメッセージを転送するときに通知します。 この状態は、侵害された管理者アカウントが新しいユーザーの作成に使用されたことを示している可能性があります。 アカウントが侵害されたと思われる場合は、「侵害された [メール アカウントへの対応」を](responding-to-a-compromised-email-account.md)参照してください。

この分析情報は、問題が検出された場合にのみ表示され、[ [転送レポート](view-mail-flow-reports.md#forwarding-report) ] ページに表示されます。

:::image type="content" source="../../media/mfi-new-users-forwarding-email.png" alt-text="電子メール分析情報を転送する新しいユーザー" lightbox="../../media/mfi-new-users-forwarding-email.png":::

ウィジェットをクリックするとポップアップが表示され、転送されたメッセージの詳細を確認できます。この記事で後述するように [、[転送の変更] レポート](#forwarding-modifications-report) へのリンクも含まれます。

:::image type="content" source="../../media/mfi-new-users-forwarding-email-details.png" alt-text="[メール分析情報を転送する新しいユーザー] をクリックした後に表示される [詳細] ポップアップ" lightbox="../../media/mfi-new-users-forwarding-email-details.png":::

[レポート **ダッシュボード** または<https://protection.office.com/insightdashboard>レポート] の [**Top insights & recommendations**] 領域で [**すべて表示**] をクリックした後、\>分析情報を選択すると、この詳細ページに移動することもできます。

[ **分析情報に関連付けられたレポートの表示** ] リンクをクリックすると、次のセクションで説明するように **[転送の変更] レポート** に移動できます。

## <a name="forwarding-modifications-report"></a>転送変更レポート

**転送変更レポートには、組織内の** 送信者から自動的に転送されるメッセージに関する詳細が表示されます。

- メッセージを外部ドメインに転送する新しく作成されたアカウント。
- 組織内の他の送信者によって転送されたことがない外部ドメインにメッセージを転送しているアカウント。

このような種類の転送されたメッセージは、セキュリティやコンプライアンスのリスクを引き起こす可能性があり、侵害されたアカウントを示している可能性があります。

レポートには、最大 90 日間のデータが含まれています。 既定では、レポートには過去 7 日間のデータが表示されます。

このレポートは、 [メール フロー ダッシュボード](mail-flow-insights-v2.md) または [レポート](view-mail-flow-reports.md) ダッシュボードでは直接使用できません。 電子メール分析情報を **転送する新しいユーザー** の **[分析情報に関連付けられたレポートの表示**] リンクをクリックするだけでなく、次の方法でレポートにアクセスできます。

- [転送される新しいドメイン](mfi-new-domains-being-forwarded-email.md)の詳細にある [**転送通知] レポート** のリンクをクリックします。
- 開く <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.

### <a name="report-view-for-the-forwarding-modifications-report"></a>転送変更レポートのレポート ビュー

レポート ビューでは、次のグラフを使用できます。

- **データを表示する: 新しい転送ユーザー:**

    :::image type="content" source="../../media/forwarding-modifications-report-new-forwarding-users.png" alt-text="[転送の変更] レポートの [新しい転送ユーザー] ビュー" lightbox="../../media/forwarding-modifications-report-new-forwarding-users.png":::

- **データを表示する: 新しい転送ドメイン:**

    :::image type="content" source="../../media/forwarding-modifications-report-new-forwarded-domains.png" alt-text="転送変更レポートの [新しい転送されたドメイン] ビュー" lightbox="../../media/forwarding-modifications-report-new-forwarded-domains.png":::

レポート ビューで [**フィルター]** をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>転送変更レポートの詳細テーブル ビュー

[ **詳細テーブルの表示**] をクリックした場合、表示される情報は、目的のグラフによって異なります。

- **データを表示する: 新しい転送ユーザー:**

  - **名前**: 送信者の電子メール アドレス。
  - **転送の種類**
  - **受信者の住所**
  - **詳細**
  - **Count**
  - **最初の転送日**

- **データを表示する: 新しい転送ドメイン:**

  - **名前**: 送信者の電子メール ドメイン。
  - **転送の種類**
  - **受信者の住所**
  - **詳細**
  - **Count**
  - **最初の転送日**

詳細テーブル ビューで [**フィルター]** をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

テーブルから行を選択すると、 **詳細ポップアップが** 表示され、次の情報が表示されます。

- **名前**: これは、送信者のメール アドレス ([ **データの表示: 新しい転送ユーザー** ] ビュー) または送信者のメール ドメイン ([ **データの表示: 新しい転送ドメイン** ] ビュー) のいずれかです。
- **転送の種類**
- **[受信者]**
- **詳細**
- **Count**
- **開始日**
- **推奨事項**: ここからリンクをクリックすると、Microsoft 365 管理センターでユーザーを管理できます。

  :::image type="content" source="../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png" alt-text="[転送の変更] レポートの [新しい転送ユーザー] ビューの詳細テーブルからの詳細ポップアップ" lightbox="../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png":::

レポート ビューに戻るには、[レポートの **表示**] をクリックします。

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
