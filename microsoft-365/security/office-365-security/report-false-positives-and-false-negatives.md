---
title: Outlook で誤検知と誤検知を報告する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Outlook で誤検知と誤検知を報告し、レポート メッセージとレポートフィッシング アドインを有効にする方法について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065174"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Outlook で誤検知と誤検知を報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Exchange Online メールボックスを使用する Microsoft 365 組織の管理者である場合は、セキュリティ & コンプライアンス センターで申請ポータルを使用することをお勧めします。 詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

ハイブリッドモダン認証を使用して Exchange Online またはオンプレミスメールボックスにメールボックスを持つ Microsoft 365 組織では、誤検知 (スパムとしてマークされた良いメール) と偽陰性 (悪い電子メールとフィッシング許可) を Exchange Online Protection (EOP) に送信できます。

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a>レポート メッセージ機能を使用する前に覚えておく必要があるもの

- 最適なユーザー申請エクスペリエンスを得る場合は、レポート メッセージ アドインまたはレポート フィッシング アドインを使用します。

- このアドインは、Web、iOS、Android、デスクトップのすべてのプラットフォームで Outlook で機能します。

- Exchange Online メールボックスを持つ組織の管理者である場合は、セキュリティ コンプライアンス センターの申請&使用します。 詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

- Microsoft、指定したメールボックス、または両方にメッセージを直接送信する構成が可能です。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。

- Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="use-the-report-message-feature"></a>レポート メッセージ機能を使用する

### <a name="report-junk-and-phishing-messages"></a>迷惑メールとフィッシング メッセージを報告する

迷惑メール以外の受信トレイまたは他のメール フォルダー内のメッセージの場合は、次の方法を使用してスパムメッセージとフィッシング メッセージを報告します。

1. 選択した **メッセージの右上隅** にある [その他の操作] 楕円をクリックし、ドロップダウン メニューから [メッセージの報告] をクリックし、[迷惑メール] または [フィッシング]**を選択します**。
  
   > [!div class="mx-imgBorder"]
   > ![レポート メッセージ - その他のアクション](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![レポート メッセージ - 迷惑メールとフィッシング](../../media/report-message-junk-phishing.png)

2. 選択したメッセージは、分析のために Microsoft に送信されます。

   - 迷惑メールとして報告された場合は、迷惑メール フォルダーに移動しました。

   - フィッシングとして報告された場合に削除されます。
   
### <a name="report-messages-that-are-not-junk"></a>迷惑メールではないメッセージを報告する

1. 選択した **メッセージの右上隅** にある [その他のアクションの省略記号] をクリックし、ドロップダウン メニューから [メッセージの報告] をクリックし、[迷惑メールではない] を **クリックします**。  

   > [!div class="mx-imgBorder"]
   > ![レポート メッセージ - その他のアクション](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![レポート メッセージ - 迷惑メールではない](../../media/report-message-not-junk.png)

2. 選択したメッセージは分析のために Microsoft に送信され、受信トレイまたは指定したその他のフォルダーに移動されます。

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a>レポート メッセージとレポートフィッシング アドインを有効にする

Outlook および Outlook on the web (以前は Outlook Web App と呼ばれる) のレポート メッセージとレポートフィッシング アドインを使用すると、ユーザーは誤検知 (悪いマークが付いた良いメール) または誤検知 (悪いメールが許可されている) を Microsoft とその関連会社に簡単に報告して分析できます。 

Microsoft では、これらの申請を使用して、電子メール保護テクノロジの有効性を向上します。 たとえば、ユーザーがレポート フィッシング アドインを使用して多くのメッセージを報告するとします。 この情報は、セキュリティ ダッシュボードや他のレポートに表示されます。 組織のセキュリティ チームは、この情報をフィッシング対策ポリシーを更新する必要がある可能性を示す指標として使用できます。 

[レポート メッセージ] アドインまたは [レポート フィッシング] アドインをインストールできます。 ユーザーがスパム メッセージとフィッシング メッセージの両方を報告する場合は、組織にレポート メッセージ アドインを展開します。 詳細については、「レポート メッセージ アドインを有効にする」を参照してください。 

レポート メッセージ アドインには、スパム メッセージとフィッシング メッセージの両方を報告するオプションがあります。 管理者は、組織のレポート メッセージ アドインを有効にし、個々のユーザーが自分でインストールできます。 

[フィッシングの報告] アドインには、フィッシング メッセージのみを報告するオプションがあります。 管理者は組織のレポート フィッシング アドインを有効にし、個々のユーザーが自分でインストールできます。 

個々のユーザーの場合は、両方のアドインを自分で有効にできます。

f グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、組織のレポート メッセージ アドインとレポート フィッシング アドインを有効にできます。 どちらのアドインも、集中展開を [通じて利用できます](../../admin/manage/centralized-deployment-of-add-ins.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- レポート メッセージ アドインとレポート フィッシング アドインの両方が、ほとんどの Microsoft 365 サブスクリプションと次の製品で動作します。

  - Outlook on the web
  - Outlook 2013 SP1 以降
  - Outlook 2016 for Mac
  - エンタープライズ向け Microsoft 365 アプリに含まれる Outlook
  - iOS と Android 用 Outlook アプリ

- 両方のアドインは、オンプレミスの Exchange 組織の共有メールボックスまたはメールボックスでは使用できません。

- 既存の Web ブラウザーは、レポート メッセージ アドインとレポート フィッシング アドインの両方で動作する必要があります。ただし、アドインが使用できないか、期待通り動作していない場合は、別のブラウザーを試してください。

- 組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。 詳細については、「アドインの集中展開が組織で機能するかどうかを判断する」 [を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。

- 管理者は、グローバル管理者役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="get-the-report-message-add-in"></a>レポート メッセージ アドインの取得

### <a name="get-the-add-in-for-yourself"></a>自分でアドインを取得する

1. [Microsoft AppSource] に移動し <https://appsource.microsoft.com/marketplace/apps> 、レポート メッセージ アドインを検索します。 レポート メッセージ アドインに直接移動するには、に移動します <https://appsource.microsoft.com/product/office/wa104381180> 。

2. [今 **すぐ取得] をクリックします**。

   ![レポート メッセージ - 今すぐ取得する](../../media/ReportMessageGETITNOW.png)

3. 表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。

4. 仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。

アドインをインストールして有効にすると、次のアイコンが表示されます。

- Outlook では、アイコンは次のように表示されます。

  > [!div class="mx-imgBorder"]
  > ![Outlook のレポート メッセージ アドイン アイコン](../../media/OutlookReportMessageIcon.png)

- Outlook on the web では、アイコンは次のように表示されます。

  > [!div class="mx-imgBorder"]
  > ![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)

### <a name="get-the-add-in-for-your-organization"></a>組織のアドインを取得する

> [!NOTE]
> アドインが組織に表示するには、最大で 12 時間かかる場合があります。

1. Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。 アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。

2. ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。

4. 次のページで、[ストアから **選択] をクリックします**。

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. 表示される **[アドインの選択] ページ** で、[検索]ボックスをクリックし、[レポート メッセージ] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。 結果の一覧で、[レポート メッセージ] **を探し、[** 追加] を **クリックします**。

   ![アドインの検索結果を選択する](../../media/NewAddInScreen3.png)

6. 表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] を **クリックします**。

7. 表示される **[アドインの構成]** ページで、次の設定を構成します。

   - **割り当てられたユーザー**: 次のいずれかの値を選択します。

     - **すべてのユーザー** (既定)
     - **特定のユーザー/グループ**
     - **私だけです**

   - **展開方法**: 次のいずれかの値を選択します。

     - **固定 (既定)**: 指定したユーザーにアドインが自動的に展開され、削除できない。
     - **利用可能**: ユーザーは、ホーム アドイン \> **の取得** 管理でアドイン \> **をインストールできます**。
     - **オプション**: アドインは指定したユーザーに自動的に展開されますが、削除を選択できます。

   ![[アドインの構成] ページ](../../media/configure-add-in.png)

   完了したら、[展開] を **クリックします**。

8. 表示される **[レポート メッセージの展開** ] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。 情報を読んだら、[次へ] を **クリックします**。

   ![[レポート メッセージの展開] ページ](../../media/deploy-report-message-page.png)

9. 表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。

   ![[アドインのアナウンス] ページ](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>レポート メッセージ アドインの設定を確認または編集する

1. Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。 アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。

   ![新しい Microsoft 365 管理センターAdd-Insの [サービスとサービス] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. レポート メッセージ アドインを **検索して** 選択します。

3. 表示される **[レポート メッセージの編集** ] フライアウトで、組織に合った設定を確認および編集します。 完了したら、**[保存]** をクリックします。

   ![レポート メッセージ アドインの設定](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>レポートフィッシング アドインを取得する

### <a name="get-the-add-in-for-yourself"></a>自分でアドインを取得する

1. [Microsoft AppSource] に移動し、レポートフィッシング <https://appsource.microsoft.com/marketplace/apps> アドインを検索します。

2. [今 **すぐ取得] をクリックします**。

3. 表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。

4. 仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。

アドインをインストールして有効にすると、次のアイコンが表示されます。

- Outlook では、アイコンは次のように表示されます。

  ![Outlook の [フィッシング アドインのレポート] アイコン](../../media/Outlook-ReportPhishing.png)

- Outlook on the web では、アイコンは次のように表示されます。

  > [!div class="mx-imgBorder"]
  > ![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)

### <a name="get-the-add-in-for-your-organization"></a>組織のアドインを取得する

> [!NOTE]
> アドインが組織に表示するには、最大で 12 時間かかる場合があります。

1. Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。 アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。

2. ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。

4. 次のページで、[ストアから **選択] をクリックします**。

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. 表示される **[アドインの選択**] ページで、[検索]ボックスをクリックし、[レポートフィッシング] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。 結果の一覧で[レポートフィッシング] **を探し、[** 追加] を **クリックします**。

6. 表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] を **クリックします**。

7. 表示される **[アドインの構成]** ページで、次の設定を構成します。

   - **割り当てられたユーザー**: 次のいずれかの値を選択します。

     - **すべてのユーザー** (既定)
     - **特定のユーザー/グループ**
     - **私だけです**

   - **展開方法**: 次のいずれかの値を選択します。

     - **固定 (既定)**: 指定したユーザーにアドインが自動的に展開され、削除できない。
     - **利用可能**: ユーザーは、ホーム アドイン \> **の取得** 管理でアドイン \> **をインストールできます**。
     - **オプション**: アドインは指定したユーザーに自動的に展開されますが、削除を選択できます。

   完了したら、[展開] を **クリックします**。

8. 表示される **[レポートフィッシングの** 展開] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。 情報を読んだら、[次へ] を **クリックします**。

9. 表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>レポートフィッシング アドインの設定を確認または編集する

1. Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。 アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。

2. [フィッシング のレポート] **アドインを検索して** 選択します。

3. 組織に **合った設定を** 表示、確認、および編集する [レポートのフィッシングの編集] フライアウトで行います。 完了したら、**[保存]** をクリックします。

## <a name="view-and-review-reported-messages"></a>報告されたメッセージの表示と確認

ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。

- 管理者申請ポータルを使用します。 詳細については [、「Microsoft へのユーザー申請の表示」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。

- 報告されたメッセージのコピーを送信するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成します。 手順については、「メール フロー ルールを使用して、ユーザーが Microsoft に報告している [情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。