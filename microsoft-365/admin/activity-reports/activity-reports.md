---
title: Microsoft 365 管理センターのアクティビティ レポート
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- adminvideo
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- GEA150
ms.assetid: 0d6dfb17-8582-4172-a9a9-aed798150263
description: 組織内のユーザーがどのように Microsoft 365 サービスを使用しているかの定期的レポートを取得して、各チャートをドリルダウンして詳しい分析情報を得ます。
ms.openlocfilehash: 05bee2950cb50b0b5a21ef67e9f73cec5e78b07a
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66601610"
---
# <a name="microsoft-365-reports-in-the-admin-center"></a>管理センターの Microsoft 365 レポート

YouTube で [Microsoft 365 Small Business ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659)を確認してください。

ユーザーが仕事でどのように Microsoft 365 サービスを使用しているかを簡単に確認できます。たとえば、サービスをかなり使用しているためにクォータに近づいているユーザーや、Microsoft 365 ライセンスをまったく必要としない可能性があるユーザーを、特定することができます。永続的ライセンス モデルがレポートに含まれます。 
  
過去 7 日、30 日、90 日、180 日間のレポートを利用できます。すべてのレポート期間のデータが最初から存在するわけではありません。レポートは、48 時間以内に使用できるようになります。

## <a name="watch-act-on-a-usage-report-in-office-365"></a>動画: Office 365 の使用状況レポートでの操作
  
[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2198103)で、このビデオや他のビデオを確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VjrX?autoplay=false]

## <a name="how-to-get-to-the-reports-dashboard"></a>レポート ダッシュボードに移動する方法

::: moniker range="o365-worldwide"

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**レポート**] \> [**使用状況**] ページの順に移動します。

::: moniker-end

2. レポートの詳細ページを表示するには、サービス (メール、OneDrive など) の概要アクティビティ カードから **[その他を表示]** ボタンをクリックします。サービスに関するさまざまなレポートがタブに表示されます。

   :::image type="content" alt-text="利用状況ダッシュボード。" source="../../media/4c0f966d-9d2b-4a6f-a106-a6e2b9a2de07.png" lightbox="../../media/4c0f966d-9d2b-4a6f-a106-a6e2b9a2de07.png":::

## <a name="who-can-see-reports"></a>レポートを閲覧できるユーザー

次の権限を持っているユーザー:

- グローバル管理者: このロールを持つのは、社内の少数のユーザーのみにすることをお勧めします。それにより業務上のリスクが軽減されます。

- Exchange の管理者

- SharePoint の管理者

- Skype for Business の管理者

- グローバル閲覧者 (ユーザーの詳細を含まない)

- 使用状況の概要レポート閲覧者 (ユーザーの詳細を含まない)

- レポート閲覧者

- Teams 管理者

- Teams 通信管理者

詳しくは、「[管理者ロールについて](../add-users/about-admin-roles.md)」および「[管理者ロールを割り当てる](../add-users/assign-admin-roles.md)」をご覧ください。

## <a name="which-activity-reports-are-available-in-the-admin-center"></a>管理センターで利用可能なアクティビティ レポート

サブスクリプションに応じて、すべての環境で以下のレポートを利用できます。

|レポート|パブリック|GCC|GCC-High|DoD|21 Vianet が運用している Office 365|
|:-----|:-----|:-----|:-----|:-----|:-----|
|[Microsoft ブラウザーの使用法](browser-usage-report.md)|はい|いいえ<sup>1</sup>|いいえ<sup>1</sup>|いいえ<sup>1</sup>|いいえ<sup>1</sup>|
|[メール アクティビティ](email-activity-ww.md)|はい|はい|はい|はい|はい|
|[メール アプリの利用状況](email-apps-usage-ww.md)|はい|はい|はい|はい|はい|
|[メールボックス使用状況](mailbox-usage.md)|はい|はい|はい|はい|はい|
|[Office ライセンス認証数](microsoft-office-activations-ww.md)|はい|はい|はい|はい|はい|
|[アクティブなユーザー](active-users-ww.md)|はい|はい|はい|はい|はい|
|[Microsoft 365 グループ](office-365-groups-ww.md)|はい|はい|はい|はい|はい|
|[Microsoft 365 Apps の使用法](microsoft365-apps-usage-ww.md)|はい|はい|いいえ<sup>1</sup>|いいえ<sup>1</sup>|はい
|[OneDrive for Business のユーザー アクティビティ](onedrive-for-business-activity-ww.md)|はい|はい|はい|はい|はい|
|[OneDrive for Business の利用状況](onedrive-for-business-usage-ww.md)|はい|はい|はい|はい|はい|
|[SharePoint サイトの利用状況](sharepoint-site-usage-ww.md)|はい|はい|はい|はい|はい|
|[SharePoint のアクティビティ](sharepoint-activity-ww.md)|はい|はい|はい|はい|はい|
|[Microsoft Teams ユーザー アクティビティ](microsoft-teams-user-activity-preview.md)|はい|はい|はい|はい|該当なし <sup>2</sup>|
|[Microsoft Teams デバイスの利用状況](microsoft-teams-device-usage-preview.md)|はい|はい|はい|はい|該当なし <sup>2</sup>|
|[Microsoft Teams の利用状況](microsoft-teams-usage-activity.md)|はい|はい|はい|はい|該当なし <sup>2</sup>|
|[Yammer アクティビティ](yammer-activity-report-ww.md)|はい|はい|該当なし <sup>2</sup>|該当なし <sup>2</sup>|該当なし <sup>2</sup>|
|[Yammer デバイスの使用状況](yammer-device-usage-report-ww.md)|はい|はい|該当なし <sup>2</sup>|該当なし <sup>2</sup>|該当なし <sup>2</sup>|
|[Yammer のグループ アクティビティ レポート](yammer-groups-activity-report-ww.md)|はい|はい|該当なし <sup>2</sup>|該当なし <sup>2</sup>|該当なし <sup>2</sup>|
|[フォームのアクティビティ](forms-activity-ww.md)|はい|はい|いいえ<sup>1</sup>|いいえ<sup>1</sup>|いいえ<sup>1</sup>|
|[Dynamics 365 顧客音声アクティビティ](forms-pro-activity-ww.md)|はい|はい|該当なし <sup>2</sup>|該当なし <sup>2</sup>|該当なし <sup>2</sup>|
|[Skype for Business Online のアクティビティ](/SkypeForBusiness/skype-for-business-online-reporting/activity-report)|はい|はい|いいえ<sup>1</sup>|いいえ<sup>1</sup>|はい|
|[Skype for Business Online の電話会議開催者のアクティビティ](/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)|はい|はい|いいえ<sup>1</sup>|いいえ<sup>1</sup>|はい|
|[Skype for Business Online の電話会議参加者のアクティビティ](/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)|はい|はい|いいえ<sup>1</sup>|いいえ<sup>1</sup>|はい|
|[Skype for Business Online のピアツーピア アクティビティ](/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)|はい|はい|いいえ<sup>1</sup>|いいえ<sup>1</sup>|はい|
|[Viva ラーニング アクティビティ](viva-learning-activity.md)|はい|該当なし|該当なし|該当なし|該当なし|
|[Viva インサイト アクティビティ](viva-insights-activity.md)|はい|はい|該当なし|該当なし|該当なし|
|[Project アクティビティ](project-activity.md)|はい|はい|該当なし|該当なし|該当なし|

該当なし <sup>1</sup>: レポートは将来リリースされる予定です。 <a href="https://www.microsoft.com/en-us/microsoft-365/roadmap?filters=" target="_blank">Microsoft 365 ロードマップ</a> はリリース前に更新されます。
該当なし <sup>2</sup>: このサービスは環境内で使用できないため、レポートをリリースする予定はありません。

## <a name="how-to-view-licensing-information"></a>ライセンス情報を表示する方法

- 割り当て済みおよび未割り当てのライセンスの数を表示するには、管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] の順に移動します。 

- ライセンスのあるユーザー、ライセンスのないユーザー、またはゲストを表示するには、管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

## <a name="how-to-view-usage-information-for-a-specific-user"></a>特定のユーザーの使用状況の情報を表示する方法

特定のユーザーがどの程度サービスを使用しているかを調べるには、サービス レポートを使います。たとえば、特定のユーザーが使っているメールボックス記憶域の量を確認するには、メールボックスの利用状況レポートを開き、ユーザーを名前で並べ替えます。ユーザーが何千人もいる場合は、レポートを Excel にエクスポートすると、一覧をすばやくフィルター処理できます。

ユーザーのアカウントを入力してから、ユーザーが使っているサービスとその使用量の一覧を取得すると、レポートを生成できません。

時には新しいユーザーが **不明** と表示される場合もあります。 これは、通常、ユーザー プロファイルの作成がときどき遅延するためです。

## <a name="show-user-details-in-the-reports"></a>レポートでユーザーの詳細を表示する

既定では、ユーザーの詳細はすべてのレポートで非表示になります。

ユーザー リストは次のように表示されます。

![レポート - 匿名ユーザー リスト。](../../media/2ed99bce-4978-4ee3-9ea2-4a8db26eef02.png)

レポートの生成時にユーザーレベルの情報を再表示する場合は、**グローバル管理者** が管理センターでその変更をすばやく行うことができます。

レポートで組織の使用状況データに関する情報を入力します。 既定では、レポートにユーザー、グループ、およびサイトの識別可能な名前を持つ情報が表示されます。 2021 年 9 月 1 日より、企業が地域のプライバシー法をサポートするのに役立つ継続的な取り組みの一環として、既定ですべてのレポートのユーザー情報を非表示にしています。

グローバル管理者は、組織のプライバシー方針で許可されている場合は、テナント用のこの変更を元に戻し、特定可能なユーザー情報を表示することができます。 これは、Microsoft 365 管理センターで以下の手順に従うことで設定できます。

1. 管理センターで、**[設定]** \> **[組織の設定]** \> **[サービス]** のページの順に移動します。

2. [**レポート**] を選択します。

3. **[すべてのレポートで非表示のユーザー、グループ、およびサイト名を表示する]** ステートメントのチェックを外し、変更を保存します。

2022 年 6 月 23 日以降、グローバル管理者が Microsoft 365 管理センターにアクセスしなくても、この設定を変更できるように、すべての環境で API が徐々に利用できるようになります。 API の詳細は次のとおりです。  

URL は https://graph.microsoft.com/beta/admin/reportSettings です 

この API では、次の 2 つのメソッドが承認されています。

:::image type="content" source="../../media/api-show-details.png" alt-text="API メソッド。":::

レポートにはプライバシー設定プロパティのみが含まれます。 Graph API の詳細については、「[Microsoft Graph API を使用する](/graph/use-the-api)」を参照してください。 グローバル管理者は、ソフトウェア開発キット (SDK) を使用するか、ネットワーク機能を備えた任意のプログラム言語を使用して API を直接呼び出すことができます。 [Graph エクスプローラー](/graph/graph-explorer/graph-explorer-overview)を使用することをお勧めします。

レポート ダッシュボードのレポートで変更が有効になるまで数分かかります。 この設定は、[Microsoft Graph](/graph/api/resources/report) と [Power BI](/microsoft-365/admin/usage-analytics/usage-analytics) の Microsoft 365 使用状況レポート、および [Microsoft Teams 管理センターの使用状況レポート](/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)にも適用されます。 特定可能なユーザー情報の表示は、Microsoft Purview コンプライアンス ポータル監査ログに記録されるイベントです。

## <a name="what-happens-to-usage-data-when-a-user-account-is-closed"></a>ユーザー アカウントが削除されたとき、使用状況データはどうなりますか?

ユーザーのアカウントを削除すると、そのユーザーの使用状況データは 30 日以内に削除されます。 そのユーザーは、有効だった期間の [アクティビティ] グラフの合計に含まれますが、[ユーザーの詳細] テーブルには表示されません。

ただし、現在の日付から最大 28 日間の特定の日を選択すると、その日のユーザーの使用状況が [ユーザーの詳細] テーブルに表示されます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 利用状況分析](../usage-analytics/usage-analytics.md) (記事)
[Microsoft 365 利用状況分析をカスタマイズする](../usage-analytics/customize-reports.md) (記事)
