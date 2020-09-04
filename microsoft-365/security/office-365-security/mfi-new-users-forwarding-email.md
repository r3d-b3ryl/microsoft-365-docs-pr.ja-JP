---
title: 新しいユーザーがメールを転送していますのインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、新しいユーザーを使用して、組織内のユーザーが新しいドメインにメッセージを転送している場合に、メールの洞察をセキュリティ & コンプライアンスセンターで転送する方法を学習できます。
ms.openlocfilehash: 4d8c88cef182ab1c521d23970797e4746e188916
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357368"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターで新しいユーザーが電子メールの洞察を転送する

組織内の新しいユーザーアカウントが、突然電子メールメッセージを外部ドメインに転送し始めたときに、疑わしいことがあります。

**メールを転送している新しいドメイン**この[セキュリティ & コンプライアンスセンター](https://protection.office.com)では、組織内で新しく作成されたユーザーが外部ドメインにメッセージを転送したときに通知します。 この条件は、新しいユーザーの作成に侵害された管理者アカウントが使用されたことを示している可能性があります。 アカウントが侵害されている疑いがある場合は、「 [危害を受けた電子メールアカウントへの対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)」を参照してください。

この洞察は、問題が検出されたときにのみ表示され、 [転送レポート](view-mail-flow-reports.md#forwarding-report) ページに表示されます。

![新しいユーザーがメールを転送していますのインサイト](../../media/mfi-new-users-forwarding-email.png)

ウィジェットをクリックすると、このトピックで後述するように、転送 [変更レポート](#forwarding-modifications-report) へのリンクを含む、転送されたメッセージの詳細を確認できるフライアウトが表示されます。

![新しいユーザーの [メールの転送] をクリックした後に表示される詳細ポップアップ](../../media/mfi-new-users-forwarding-email-details.png)

また、[詳細] を選択した後に [詳細] を選択すると、[詳細] を選択した後に、[詳細] を選択したときに、この詳細ページ**を表示でき**ます (**レポート**ダッシュボードまたは) の [**上位の分析 &** \> **Dashboard** <https://protection.office.com/insightdashboard>

次のセクションで説明するように、[ **洞察に関連付けられたレポート** ] リンクをクリックして、 **転送変更レポート** に移動できます。

## <a name="forwarding-modifications-report"></a>変更の転送レポート

**転送変更レポート**には、組織内の送信者から自動的に転送されるメッセージの詳細が表示されます。

- 新たに作成されたアカウントで、外部ドメインにメッセージを転送します。
- 組織内の他の送信者によって転送されたことがない外部ドメインにメッセージを転送するアカウント。

これらの種類の転送メッセージは、セキュリティまたはコンプライアンスのリスクを引き起こす可能性があり、侵害されたアカウントを示す場合があります。

レポートには、最大90日間のデータが含まれています。 既定では、このレポートには過去7日間のデータが表示されます。

このレポートは、 [メールフローダッシュボード](mail-flow-insights-v2.md) または [レポートダッシュボード](view-mail-flow-reports.md)では直接使用できません。 **新しいユーザーが電子メールを転送**する場合は、「サイトに**関連付けられたレポートを表示する」** リンクをクリックするだけでなく、次の方法でレポートにアクセスできます。

- [転送される新しいドメイン](mfi-new-domains-being-forwarded-email.md)の詳細については、「**通知の転送レポート**」リンクをクリックしてください。
- 開いて <https://protection.office.com/reportv2?id=MailFlowNewForwarding> います。

### <a name="report-view-for-the-forwarding-modifications-report"></a>転送変更レポートのレポートビュー

次のグラフがレポートビューで利用できます。

- **データの表示: 新しい転送ユーザー**:

  ![転送変更レポートでの新しい転送ユーザーの表示](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **データの表示: 新しい転送ドメイン**:

  ![転送変更レポートの [転送された新しいドメインの表示形式](../../media/forwarding-modifications-report-new-forwarded-domains.png)

レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>転送変更レポートの詳細テーブルビュー

[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。

- **データの表示: 新しい転送ユーザー**:

  - **Name**: 送信者の電子メールアドレス。
  - **転送の種類**
  - **受信者のアドレス**
  - **詳細**
  - **Count**
  - **最初の繰越日付**

- **データの表示: 新しい転送ドメイン**:

  - **Name**: 送信者の電子メールドメイン。
  - **転送の種類**
  - **受信者のアドレス**
  - **詳細**
  - **Count**
  - **最初の繰越日付**

詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。

表から行を選択すると、 **詳細** ポップアップが次の情報と共に表示されます。

- **Name**: これは、送信者の電子メールアドレス ([ **データの表示: 新しい転送ユーザービュー]** ) または送信者の電子メールドメイン ([ **データの表示元: 新しい転送ドメインビュー]** ) のいずれかです。
- **転送の種類**
- **[受信者]**
- **詳細**
- **Count**
- **開始日**
- **推奨事項**: ここからリンクをクリックすると、Microsoft 365 管理センターでユーザーを管理できます。

![転送変更レポートの新しい転送ユーザー表示の詳細表からの詳細ポップアップ](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

レポートビューに戻るには、[ **レポートの表示**] をクリックします。

## <a name="related-topics"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
